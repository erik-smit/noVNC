# noVNC: aten basterdization

## Notes

### RFB client message types  

|  Hex   | Dec  |  Function                          |
|--------|------|------------------------------------|
|  0x04  |  4   |  RFBProtocol::KeyEvent             |
|  0x05  |  5   |  RFBProtocol::PointerEvent         |
|  0x07  |  7   |  RFBProtocol::ResyncMouseEvent     |
|  0x08  |  8   |  RFBProtocol::KMHotPlugEventEvent  |
|  0x14  |  20  |  RFBProtocol::QualityChangeEvent   |
|  0x15  |  21  |  RFBProtocol::VideoPosEvent        |
|  0x16  |  22  |  RFBProtocol::SyncKBLed            |
|  0x16  |  22  |  RFBProtocol::KeepAliveEvent       |
|  0x18  |  24  |  RFBProtocol::BrCrChangeEvent      |
|  0x19  |  25  |  RFBProtocol::FrontGroundEvent     |
|  0x1a  |  26  |  RFBProtocol::SetPowerOnOff        |
|  0x32  |  50  |  RFBProtocol::VideoSetInfo         |
|  0x33  |  51  |  RFBProtocol::VideoGetInfo         |
|  0x34  |  52  |  RFBProtocol::KeyboardSetInfo      |
|  0x35  |  53  |  RFBProtocol::KeyboardGetInfo      |
|  0x36  |  54  |  RFBProtocol::MouseSetInfo         |
|  0x37  |  55  |  RFBProtocol::MouseGetInfo         |
|  0x38  |  56  |  RFBProtocol::PutSessionMsg        |
|  0x3a  |  58  |  RFBProtocol::KMHotPlug            |
|  0x3b  |  59  |  RFBProtocol::SetStreamQos         |
|  0x3c  |  60  |  RFBProtocol::GetViewerLang        |
|  0x3d  |  61  |  RFBProtocol::SetViewerLang        |
|  0x3e  |  62  |  RFBProtocol::GetKBLedStatus       |

### RFB server message types  
