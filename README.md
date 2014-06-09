# noVNC: aten basterdization

## Aten protocol notes

### RFB client -> server messages  

| Hex  | Dec |               Function              |                                      Params                                     | Server Response Message |
| ---- | --- | ----------------------------------- | ------------------------------------------------------------------------------- | ----------------------- |
| 0x03 | 3   | RFBProtocol::FramebufferUpdateEvent | u8, u16, u16, u16, u16                                                          | 0x0                     |
| 0x04 | 4   | RFBProtocol::KeyEvent               | u8, u8, 2 bytes padding, u32, 9 bytes padding                                   | None                    |
| 0x05 | 5   | RFBProtocol::PointerEvent           | u8, u8, u16, u16, 11 bytes padding                                              | None                    |
| 0x07 | 7   | RFBProtocol::ResyncMouseEvent       | u16                                                                             | None                    |
| 0x08 | 8   | RFBProtocol::KMHotPlugEventEvent    | u8                                                                              | None                    |
| 0x14 | 20  | RFBProtocol::QualityChangeEvent     | u16                                                                             | None                    |
| 0x15 | 21  | RFBProtocol::VideoPosEvent          | u32, u32                                                                        | None                    |
| 0x16 | 22  | RFBProtocol::SyncKBLed              | u8                                                                              | 0x16                    |
| 0x16 | 22  | RFBProtocol::KeepAliveEvent         | u8                                                                              | 0x16                    |
| 0x18 | 24  | RFBProtocol::BrCrChangeEvent        | u16                                                                             | None                    |
| 0x19 | 25  | RFBProtocol::FrontGroundEvent       | None                                                                            | 0x4                     |
| 0x1a | 26  | RFBProtocol::SetPowerOnOff          | u8                                                                              | None                    |
| 0x32 | 50  | RFBProtocol::VideoSetInfo           | u16, u16                                                                        | None                    |
| 0x33 | 51  | RFBProtocol::VideoGetInfo           | None                                                                            | 0x33                    |
| 0x34 | 52  | RFBProtocol::KeyboardSetInfo        | u8, u8                                                                          | None                    |
| 0x35 | 53  | RFBProtocol::KeyboardGetInfo        | None                                                                            | 0x35                    |
| 0x36 | 54  | RFBProtocol::MouseSetInfo           | u8, u8                                                                          | None                    |
| 0x37 | 55  | RFBProtocol::MouseGetInfo           | None                                                                            | 0x37                    |
| 0x38 | 56  | RFBProtocol::PutSessionMsg          | u32, u32, 0x40 bytes                                                            | None                    |
| 0x3a | 58  | RFBProtocol::KMHotPlug              | None                                                                            | None                    |
| 0x3b | 59  | RFBProtocol::SetStreamQos           | u32, u32, u32                                                                   | None                    |
| 0x3c | 60  | RFBProtocol::GetViewerLang          | None                                                                            | 0x3c                    |
| 0x3d | 61  | RFBProtocol::SetViewerLang          | u32, u32                                                                        | None                    |
| 0x3e | 62  | RFBProtocol::GetKBLedStatus         | None                                                                            | 0x3e                    |


### RFB server -> client messages

| Hex  | Dec | Function                            | Params                                                                          |                         |
| ---- | --- | ----------------------------------- | ------------------------------------------------------------------------------- | ----------------------- |
| 0x0  |   0 | RFBProtocol::FramebufferUpdateEvent | 1 byte padding, u16, u16, u16, u16, u16, u32, u32, u32 (datalen), datalen bytes |                         |
| 0x4  |   4 | RFBProtocol::FrontGroundEvent       | u32, u32, u32, u32, u32                                                         |                         |
| 0x16 |  22 | RFBProtocol::KeepAliveEvent         | u8                                                                              |                         |
| 0x33 |  51 | RFBProtocol::VideoGetInfo           | u16, u16                                                                        |                         |
| 0x35 |  53 | RFBProtocol::KeyboardGetInfo        | u8, u8                                                                          |                         |
| 0x37 |  55 | RFBProtocol::MouseGetInfo           | u8, u8, u8                                                                      |                         |
| 0x3c |  60 | RFBProtocol::GetViewerLang          | u32, u32                                                                        |                         |
| 0x3e |  62 | RFBProtocol::GetKBLedStatus         | u8                                                                              |                         |


