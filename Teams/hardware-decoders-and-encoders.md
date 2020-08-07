---
title: ハードウェア デコーダー/エンコーダー ドライバーの推奨事項
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/06/2019
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-voice
localization_priority: Normal
search.appverid: MET150
description: ドライバーの問題が原因で、ハードウェアアクセラレータに対応していないオペレーティングシステム、モデル、およびドライバーの組み合わせを一覧表示します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a195eddc1b48ab99a995ad4ae6fa19279ff0ecf
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583164"
---
# <a name="hardware-decoder-and-encoder-driver-recommendations"></a>ハードウェア デコーダー/エンコーダー ドライバーの推奨事項

Microsoft は、この記事に記載されているものを除き、すべてのデコーダーとエンコーダーをサポートしています。

## <a name="hardware-decoder-driver-recommendations---intel"></a>ハードウェアデコーダードライバーの推奨事項-Intel

さまざまなドライバーの問題により、オペレーティングシステム、モデル、ドライバーの次の組み合わせは、ハードウェアアクセラレータでは有効になりません。

|オペレーティング システム           | Model (Device_id) | ドライバー/レンジ |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0116 | [2, 0, 11929] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0126 | [0.0.0.0]-[8.15.10.2418] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [0.0.0.0]-[8.15.10.2753] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x2772 | [8.15.10.1749] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0162、0x0162 | [0.0.0.0]-[9.17.10.2850] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [9.17.10.2867] - [9.17.10.4459] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 |0x1616 | [9.18.7.9] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [10.18.10.3431] - [10.18.10.4425] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [10.18.14.4280] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x1616 |[10.18.15.4256] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x1916 |[10.18.15.4293] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての |[10.18.15.4281] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての |[20.19.15.4390] - [20.19.15.4444] |
|Windows 10 | すべての | [21.20.16.4541] |
|Windows 10 | すべての | [22.20.16.4811] |
|Windows 10 | すべての | [24.20.100.6293] |

## <a name="hardware-decoder-driver-recommendations---nvidia"></a>ハードウェアデコーダードライバーの推奨事項-Nvidia

さまざまなドライバーの問題により、オペレーティングシステム、モデル、ドライバーの次の組み合わせは、ハードウェアアクセラレータでは有効になりません。

|オペレーティング システム           | Model (Device_id) | ドライバー/レンジ |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0540 | [8.15.1.1243] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A20 | [8.15.11.8627], [8.15.11.8634], [8.15.11.8642] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A34 | [8.15.11.8631], [8.15.11.8636], [8.15.11.8652], [8.15.11.8662], [8.15.11.8664], [8.16.11.8691] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A74 | [8.15.11.8636], [8.15.11.8652], [8.15.11.8688] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A28 | [8.15.11.8644] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A69 | [8.16.11.8691] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A3C | [0.0.0.0]-[8.17.12.6721] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0873 | [8.17.12.8562] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x040C、0x042 9、0X0429 | [0.0.0.0]-[8.17.12.9670] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [8.17.11.9745], [8.17.12.5738] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x0A2B | [0.0.0.0]-[9.18.13.282] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x087D | [9.18.13.697] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x1040 |[0.0.0.0]-[9.18.13.1106] |
|Windows 10 | すべての | [10.18.13.5891] - [10.18.13.6881] |
|Windows 10 | すべての | [21.21.13.6909], [21.21.13.7570] |
|Windows 7 | すべての | [21, 21, 13, 4201] |

## <a name="hardware-decoder-driver-recommendations---amd"></a>ハードウェアデコーダードライバーの推奨事項-AMD

従来のオペレーティングシステムでは、次の Device_ids のみがハードウェアアクセラレータに対応しています。

|オペレーティング システム           | Model (Device_id) |
|---------------------------|-------------------|
|Windows 7/<br>Windows 8/<br>Windows 8.1 | 0x9874、0x9851、0x9851、0x9851、0x9851、0x9851、0x985 7、0x9851、0x9851、0x985 a、0X9851、0x9851、0x9851、0X9851 0X9851、0X9851、0X9851、0X9874, 0x67DF, 0X9874, 0x67C2, 0x67D0, 0x67EF, 0x67FF, 0x67E0, 0x67ff, 0x67E8, 0x67の 1, 0x67e8, 0x67の, 0x Eb 0x67DF、0x67EF、0x67FF、0x6981、0x6981、0x60x0000、0x6の3、0x6981、0x6981、0x6981、0x6981、0x6981、0x6981、0x6981、0x6981、0x6981、0x6981、0X6981、0X6981、0X6981、0X6981、0X6981、0X6981、0X6981、0x69A3、0X6981、0x66A0、0x66A1 を取得します, 0x66A2, 0X66a2 |

さまざまなドライバーの問題により、オペレーティングシステム、モデル、ドライバーの次の組み合わせは、ハードウェアアクセラレータでは有効になりません。

|オペレーティング システム           | Model (Device_id) | ドライバー/レンジ |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [0.0.0.0] – [25.20.15017.1009] |

## <a name="hardware-encoder-driver-recommendations---intel"></a>ハードウェアエンコーダードライバーの推奨事項-Intel

さまざまなドライバーの問題により、オペレーティングシステム、モデル、ドライバーの次の組み合わせは、ハードウェアアクセラレータでは有効になりません。

|オペレーティング システム           | Model (Device_id) | ドライバー/レンジ |
|---------------------------|-------------------|--------------|
|Windows 7 | すべての | [8.15.10.2200] - [8.15.10.2600] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [8.15.10.2653] - [8.15.10.2827] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [9.14.3.1176] - [9.14.3.1177] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [9.17.10.2800] - [9.17.10.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [9.18.10.3222] |
|Windows 7 | すべての | [9.18.10.3234] |
|Windows 7 | すべての | [9.18.10.3272] |
|Windows 7 | すべての | [10.18.10.3242] - [10.18.10.9999] |
|Windows 8/Windows 8.1/Windows 10 | すべての | [10.18.10.0000] - [10.18.10.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [10.18.14.4153] - [10.18.14.4161] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [10.18.14.4264] |
|Windows 7 | すべての | [10.18.14.4578] |
|Windows 7 | すべての | [10.18.14.4889] |
|Windows 7 | すべての | [10.18.14.5057] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [20.19.15.4300] - [20.19.15.4444] |
|Windows 7 | すべての | [20.19.15.4474] |

## <a name="hardware-encoder-driver-recommendations---nvidia"></a>ハードウェアエンコーダードライバーの推奨事項-Nvidia

さまざまなドライバーの問題により、オペレーティングシステム、モデル、ドライバーの次の組み合わせは、ハードウェアアクセラレータでは有効になりません。

|オペレーティング システム           | Model (Device_id) | ドライバー/レンジ |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [0.0.0.0]-[21.21.13.7848] |

## <a name="hardware-encoder-driver-recommendations---amd"></a>ハードウェアエンコーダードライバーの推奨事項-AMD

従来のオペレーティングシステムでは、次の Device_ids のみがハードウェアアクセラレータに対応しています。

|オペレーティング システム           | Model (Device_id) |
|---------------------------|-------------------|
|Windows 7 | 0x9874、0x9850、0x985 1、0x985 2、0x9850、0x9850、0x985 5、0x9850、0x9850、0x9850、0x9850、0x9850、0x9850、0x9850、0x9850、0x9850、0x9850、0x9874、0x9874、0x67c1、0x9874、0x67c6、0x9874、0x67c6、0x9874、0x9874、0x9874、0x67、0x67cb、0x cc、0x67cd、0x67ce、0x67の cf、0x67d0、0x9874、0x67d4、0x67d5、0x67d4、0x9874、0x9874、0x9874、0x9874、0x9874、0x9874 0x67dc、0x67dd、0x67de、0x67df、0x67の1、0x67の、0x67e5、0x67の 4, 0x67e5, 0x67e6, 0x67e5, 0x67e8, 0x67の 1, 0x67の e 67、0x67EB、0X67eb、0X67eb、0X67eb、0X67eb、0X67eb、0x67eb 0x67eb F2、0x67F3、0X67eb、0x67F5、0x67F6、0x67F7、0X67eb、0X67eb、0X67eb、0x67eb ドライブ、0X67eb、0X67eb、0x1304、0x1305、0x1304、0x1307、0x1304、0x1307、0x1306、0x130、0x130B、0x130C、0x130D、0x130E、0x130F、0x1310、0x1311、0x1312、0x1313、0x1314、0x1315、0x1316、0x1317、0x1318、0x1319、0x131A、0x131B、0x131C、0x131D、0x131E、0x131F、66, 0X67eb, 0X67eb, 0x66A3, 0X67eb, 0x6860, 0x6860, 0x6860, 0x6860, 0x6860, 0x6860, 0x6860、0x6867、0x6867、0X6867、0X6867、0x6867、0X6867、0X6867、0X6867、0X6867、0x699、0X6867、0x69A3、0x6867 Af

さまざまなドライバーの問題により、オペレーティングシステム、モデル、ドライバーの次の組み合わせは、ハードウェアアクセラレータでは有効になりません。

|オペレーティング システム           | Model (Device_id) | ドライバー/レンジ |
|---------------------------|-------------------|--------------|
|Windows 7/Windows 8/Windows 8.1/Windows 10 | 0x674a | [0.0.0.0] – [99.9999.9999.9999] |
|Windows 7 | すべての | [0.0.0.0]-[16.199.9999.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [15.21.0.0] - [16.199.9999.9999] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [15.201.1101.0] |
|Windows 7/Windows 8/Windows 8.1/Windows 10 | すべての | [21.19.137.1] |

## <a name="related-topics"></a>関連トピック

[Teams アプリのハードウェア要件](hardware-requirements-for-the-teams-app.md)
