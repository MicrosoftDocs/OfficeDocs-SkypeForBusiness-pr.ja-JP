---
title: Teams 管理センターでライセンスの概要をMicrosoft Teams Roomsする
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Teams 管理センターでTeams Roomsライセンスと機能の可用性について説明し、比較します。
ms.openlocfilehash: d88e7a0c0a6c17fb22f1cc94fcd4de65a3ff79a2
ms.sourcegitcommit: 732a7f3e120cfa221d42b4e8af2cf9ff623488a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2022
ms.locfileid: "67633637"
---
# <a name="microsoft-teams-rooms-license-overview-in-teams-admin-center"></a>Teams 管理センターでライセンスの概要をMicrosoft Teams Roomsする

Teams 管理センターでは、Teams Rooms デバイスとその周辺機器を一元的な場所から表示および管理できます。 この記事では、Teams Rooms デバイスに Microsoft Teams Rooms Basic ライセンスと Microsoft Teams Rooms Pro ライセンスのどちらが割り当てられているかに応じて、どのような[管理機能](#comparison-of-teams-rooms-feature-availability-by-license)があるかについて説明します。

Microsoft Teams Rooms ライセンスの詳細については、「[Microsoft Teams Rooms ライセンス](rooms-licensing.md)」を参照してください。

## <a name="see-which-licenses-are-assigned-to-teams-rooms-devices"></a>Teams Rooms デバイスに割り当てられているライセンスを確認する

Teams 管理センターの Teams デバイスに移動し、表示するデバイス カテゴリ (Windows のTeams Rooms、Android のTeams Rooms、Surface Hubs) を選択すると、デバイスのライセンスを確認できます。 たとえば、**Windows で Teams** **デバイス** > Teams Roomsを選択すると、次の図のようになります。 **[ライセンス]** 列には、各デバイスに割り当てられているTeams Roomsライセンスが表示されます。

:::image type="content" source="../media/mtr-device-inventory-license-focus.png" alt-text="Standard、Pro、および Pro (Trial) ライセンスに焦点を当てたインベントリ リストをTeams Roomsします。":::

**Pro** ライセンスを持つデバイスは、Teams 管理センターのすべての機能にアクセスできます。 他のライセンスを持つデバイスは、これらの機能のサブセットにアクセスできます。 各ライセンスで使用できる機能は、ライセンス別の[Teams Rooms機能の可用性の比較で](#comparison-of-teams-rooms-feature-availability-by-license)確認できます。

> [!IMPORTANT]
> Microsoft Teams Rooms Basic ライセンスとMicrosoft Teams Rooms Pro ライセンスの両方を含む複数のデバイスを選択した場合、Microsoft Teams Rooms Pro ライセンスを必要とするアクションは、そのライセンスが割り当てられているデバイスでのみ実行されます。 このアクションは、Microsoft Teams Rooms Basic ライセンスが割り当てられているデバイスでは実行されません。

## <a name="see-which-features-require-a-microsoft-teams-rooms-pro-license"></a>Microsoft Teams Rooms Pro ライセンスが必要な機能を確認する

Microsoft Teams Rooms Pro ライセンスを必要とする機能は、デバイスの詳細ページでアイコンを探:::image type="icon" source="../media/mtr-pro-icon.png" border="false":::すことで識別できます。 現在選択されているデバイスに Microsoft Teams Rooms Pro ライセンスが割り当てられていない場合は、操作を実行できず、アップグレードのプロンプトが表示されます。

:::image type="content" source="../media/mtr-restart-device-dialog.png" alt-text="Teams Roomsデバイスの再起動ダイアログに Pro アイコンが表示されます。":::

## <a name="comparison-of-teams-rooms-feature-availability-by-license"></a>ライセンス別のTeams Rooms機能の可用性の比較

次の表は、Microsoft Teams Rooms ライセンスごとに Teams 管理センターで使用できる管理機能を示しています。

|                                               | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
|:----------------------------------------------|:---------------------------:|:-------------------------:|
| **デバイスの自動更新**                  | &#x2714;                    | &#x2714;                  |
| **基本的なデバイス分析**                    | &#x2714;                    | &#x2714;                  |
| **基本的なデバイスの正常性**                       | &#x2714;                    | &#x2714;                  |
| **通話品質ダッシュボード**                    | &#x2714;                    | &#x2714;                  |
| **ワークスペースを作成して表示する**                | &#x2714;                    | &#x2714;                  |
| **リアルタイムテレメトリ**                       | &#x2714;                    | &#x2714;                  |
| **通常の機能更新プログラム**                   | &#x2714;                    | &#x2714;                  |
| **リモート サインインとサインアウト**               | &#x2714;                    | &#x2714;                  |
| **Android デバイスの構成**             |                             | &#x2714;                  |
| **デバイス アラート**                             |                             | &#x2714;                  |
| **デバイス分析 - 正常性と使用率** |                             | &#x2714;                  |
| **デバイスの詳細ビュー**                        |                             | &#x2714;                  |
| **デバイスの正常性の詳細**                     |                             | &#x2714;                  |
| **デバイス タグ**                               |                             | &#x2714;                  |
| **Graph API**                                |                             | &#x2714;                  |
| **手動のデバイス更新プログラム**                     |                             | &#x2714;                  |
| **リモート再起動**                            |                             | &#x2714;                  |
| **Windows デバイス周辺機器の管理**     |                             | &#x2714;                  |
| **Windows デバイスの設定**                   |                             | &#x2714;                  |
