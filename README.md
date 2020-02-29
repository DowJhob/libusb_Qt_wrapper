# libusb_Qt_wrapper

Пример использования
```
libusb_async_reader *usb;
usb = new libusb_async_reader();
QObject::connect( usb, SIGNAL(readyRead(QByteArray)), this, SLOT(read_barcode_snapi(QByteArray)) );
```

VID:PID прибиты гвоздями внутри, libusb_async_reader запускает поток со своим циклом обработки коряво но работает и не выжирает CPU избыточным поллингом, по хорошему надо тщательно разобраться с циклом обработки событий libusb и не запускать лишний поток
