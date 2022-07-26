# Silent print

This service allows you to print files with a GET request through port 8081.
It also allows you to obtain the private IP of the device according to the mask (very useful in the case of registering impressions).

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Installing](#installing)
- [Usage](#usage)
  - [Get IP address according to mask](#get-ip-address-according-to-mask)
  - [Printing files](#printing-files)
- [Acknowledgements](#acknowledgements)
- [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Installing

Now is working only on Windows (8081 port):

`Download and install`

## Usage

Once installed, it will start automatically and create a "Silent Print Service" shortcut. You can add it to autostart programs. If the service is running and you try to open it again from the shortcut, it will show a port error, since the port was previously occupied by the service.

It is essential to have port 8081 free.

Example request:

#### Get IP address according to mask

Returns all the ip of the device that have the mask 24 (Ethernet, Wi-Fi, Virtual Machine, Others).

You can put your netmask number in the request and you will receive the IP contained in it from your device

```
http://localhost:8081/ip/24

```

#### Printing files

You can print files that have extension `.pdf .doc .docx .txt`. The files must be contained in the "Downloads" folder.

You do not need to specify the name of the printer to complete the process. The service takes the default printer to send the print.

When you try to print a file that does not exist you will receive a 404 error code.

```
http://localhost:8081/print/test-printing.pdf

```

## Acknowledgements

This is inspired by [PDFtoPrinter](http://www.columbia.edu/~em36/pdftoprinter.html)

## License

MIT
