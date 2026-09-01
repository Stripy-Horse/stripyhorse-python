# Stripy Horse Python SDK

Official Python client for the [Stripy Horse](https://stripyhorse.io) API - Zebra/ZPL
developer tools: render ZPL to PNG, convert PDFs/images/HTML to print-ready ZPL,
and drive hosted virtual Zebra printers from your tests.

Generated from the live [OpenAPI spec](https://stripyhorse.io/openapi.yaml), which is
itself emitted from the server's handler code, so the SDK can never drift from the API.

Requires Python 3.9+.

## Install

```bash
pip install stripyhorse
```

## Setup

```python
import stripyhorse
from stripyhorse.api import ConvertApi, RenderApi, SimulatorApi
from stripyhorse.models import RenderInputBody, HtmlInputBody, CreatePrinterInputBody, Faults

config = stripyhorse.Configuration(access_token="sh_live_YOUR_KEY")
client = stripyhorse.ApiClient(config)
```

## Render ZPL to PNG

```python
import base64

render = RenderApi(client)
out = render.render_zpl(RenderInputBody(
    zpl="^XA^FO50,50^A0N,45,45^FDHello^FS^XZ", preset="4x6"))
with open("label.png", "wb") as f:
    f.write(base64.b64decode(out.labels[0].png))
```

## Convert a PDF (or PNG/GIF/JPEG) to ZPL

```python
convert = ConvertApi(client)
result = convert.convert_document(file="shipping-label.pdf", preset="4x6")
for page in result.pages:
    send_to_printer(page.zpl)
```

## Design a label in HTML, get ZPL

```python
out = convert.convert_html(HtmlInputBody(
    html='<div style="position:absolute;left:40px;top:40px;font-size:50px">Hello</div>',
    preset="4x6"))
print(out.zpl)
```

## Test label printing in CI with a virtual printer

```python
sim = SimulatorApi(client)

printer = sim.create_printer(CreatePrinterInputBody(name="ci-run-42", preset="4x6"))

# Point the system under test at the printer, exactly like hardware:
addr = f"{printer.tcp.host}:{printer.tcp.port}"

# ... run your fulfillment code against addr ...

# Then assert on what it printed:
jobs = sim.list_jobs(printer.id)
assert len(jobs.jobs) == 1

# Reproduce a paper-out jam and watch jobs hold in the buffer:
sim.set_printer_faults(printer.id, Faults(paper_out=True))
```

## Errors

API errors raise `stripyhorse.ApiException`; `e.body` carries the JSON error
envelope. HTTP 429 includes a `Retry-After` header.

## Regenerating

Every file here is generated from the [OpenAPI spec](https://stripyhorse.io/openapi.yaml),
which is emitted from the server's own handler code. Hand edits are overwritten by the
next spec change, so report a problem with the SDK as a problem with the API:
[stripyhorse.io/contact](https://stripyhorse.io/contact).
