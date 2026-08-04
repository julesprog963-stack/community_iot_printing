# Community IoT Printing

`community_iot_printing` is a free LGPL-3 Odoo Community addon from JDA
SOLUTIONS for sending QWeb PDF reports to printers managed by IoT Box
Community.

## Compatibility and dependency

Use the branch matching your Odoo version:

- Odoo 17: `community_iot_box` `17.0.5.0.0` — https://apps.odoo.com/apps/modules/17.0/community_iot_box
- Odoo 18: `community_iot_box` `18.0.2.0.0` — https://apps.odoo.com/apps/modules/18.0/community_iot_box
- Odoo 19: `community_iot_box` `19.0.2.0.0` — https://apps.odoo.com/apps/modules/19.0/community_iot_box

The matching `community_iot_box` release must be installed before this
addon. The external Community IoT Agent 0.4.0 must advertise `pdf_print_v1`
and have an online Standard Printer available.

## Features

- separate **IoT Print** action for applicable QWeb PDF reports;
- form and list selection, up to 100 records per operation;
- report rendering with the current user's permissions, company, language and
  context;
- assistant for printer, filename and 1 to 10 copies;
- one independent IoT job per copy for retries and idempotency;
- dedicated **Community IoT Print User** group;
- administrator-only default-printer configuration;
- the standard Odoo **Print** menu remains unchanged.

The addon does not depend on Sales, Inventory, Accounting or Point of Sale.
POS receipts and preparation flows remain in the separate
`pos_community_iot` repository.

## Installation

1. Install `community_iot_box` from the matching branch.
2. Copy `community_iot_printing` into the custom addons path.
3. Update the Apps list and install **Community IoT Printing**.
4. Add users who need the action to **Community IoT Print User**.
5. Register an online IoT Box with a Standard Printer advertising
   `pdf_print_v1`.
6. Open a quotation, invoice, delivery or another model with a QWeb PDF
   report and choose **IoT Print**.

## Seguridad / Security

Los PDF se conservan temporalmente en una attachment protegida y el trabajo
solo contiene metadatos y una ruta de descarga protegida por el token de la
caja y el lock token del job. No se registran tokens ni contenido de PDF.

PDF files are stored temporarily in a protected attachment. The job contains
only metadata and a download route protected by the box token and job lock
token. Tokens and PDF content are never written to logs.

## Documentation / Documentación

- English: `community_iot_printing/doc/index.rst`
- Español: `community_iot_printing/doc/index.es.rst`

## License

LGPL-3
