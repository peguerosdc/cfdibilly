# cfdibilly
[![PyPI Latest Release](https://img.shields.io/pypi/v/cfdibilly.svg)](https://pypi.org/project/cfdibilly/)

Utility to inspect and validate CFDI (Mexican invoice) versions 3.3 and 4.0

## Features

* Load a CFDI (any XML) into a python dictionary
* Gather the status of a CFDI from SAT
* **Doesn't require** additional dependencies to read XML like libxml2-dev, libxslt-dev

## Installation

Run:

```sh
pip install cfdibilly
```

## Examples

You can load a verify an invoice directly from its XML:

````python
import cfdibilly

file = "invoice.xml"
cfdi = cfdibilly.read_xml(file)
status = cfdibilly.verify(cfdi)
````

Or you can verify an invoice manually:

````python
import cfdibilly

cfdibilly.verify(uuid="folio fiscal", rfc_emisor="re", rfc_receptor="rr", total_facturado=150.00)
````

## License

Licensed under the [GNU LGPLv3 License](https://github.com/peguerosdc/cfdibilly/blob/master/LICENSE).