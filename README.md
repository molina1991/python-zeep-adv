## Zeep-adv: Python SOAP client + mtom with mime type management

Based on : http://docs.python-zeep.org/  
And this mtom extention : https://github.com/mvantellingen/python-zeep/pull/314/files

`pip install python-zeep-adv`

```python

from zeep import Client
from zeep.transport_with_attach import TransportWithAttach

transport_with_attach = TransportWithAttach()
client = Client('tests/wsdl_files/example.rst', transport=transport_with_attach)  # Insert your wdsl file path

factory = client.type_factory("ns1")  # ns1 by defautl, may be different according to your wsdl file

soap_data = client.attach("/path/to/some.file")  # file you want to send as attachment
self.yourComplexeType(binary64fieldname=data_doc)  # Create the complexe type element and attach the file

```

This was developed for a specific usage and this code should not be used for other puposes has it.  
(or at your own risks ;) )

