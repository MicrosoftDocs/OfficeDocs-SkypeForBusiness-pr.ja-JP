---
title: Teams ストア
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: rahulimi
ms.topic: article
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
description: 管理センターのデバイス ストアでデバイスを参照Teams購入する方法について確認する
ms.openlocfilehash: f83fd22192a8145167ff04a2bd73b88746dd3ce7
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64457080"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>デバイス ストアでデバイスTeams購入する

>[!NOTE]
>現在Teamsデバイス ストアはパブリック プレビューでのみ **使用できます**。 パブリック プレビューでは、今後の機能をテストし、フィードバックを提供できます。 パブリック プレビューに含まれる機能は、完全ではなく、変更される可能性があります。また、Office 365 Government Cloud ではサポートされていません。

Teams 管理センターのデバイス ストアでは、認証を受けたデバイスを参照、購入、プロビジョニングMicrosoft Teams。  

 管理センターでデバイス ストアを使用Teams、[デバイスとストア] **>します**。

## <a name="requirements"></a>要件

デバイス ストアを使用するには、グローバル管理者、管理者、またはTeams管理者Teams必要があります。

## <a name="browse-the-store"></a>ストアを参照する

デバイス ストアには、ヘッドセット、Web カメラ、Teams 会議室、デスク フォン、Teams ディスプレイなどの Teams デバイスなど、Teams の認定を受けたすべてのデバイスが含まれています。 並べ替え、フィルター、または検索を行って、組織に必要なデバイスを検索できます。

## <a name="purchase-devices"></a>デバイスを購入する

デバイス ストアからデバイスを購入すると、配送と配送を含む支払いおよびフルフィルメントは、Microsoft サード パーティのフルフィルメント パートナーである UnifiedCommunications.com によって処理されます。  

クレジット カードまたは発注書でお支払いください。 発注書の支払いには、フルフィルメント プロバイダーで 1 回のセットアップが必要です。

すべての注文は、配送後最大 30 日後に返されます。

## <a name="data-handling-and-sharing"></a>データの処理と共有

Teams デバイス ストアでは、Teams 管理センターで購入を有効にするには、ユーザーとテナントの GUID などの基本的なユーザーと会社の情報を UnifiedCommunications.com と共有する必要があります。

データ共有は既定で無効になっています。 有効にするには、デバイス ストアの [Teams] に移動し、設定アイコンを選択して、設定をオンにします。  

この設定がオフの場合、データは共有されません。また、Teams デバイス ストアを参照できますが、購入を行う必要があります。 設定がオンの間にフルフィルメント プロバイダーと収集および共有されたデータは、プライバシーに関する声明で指定されている方法で処理されます。

## <a name="order-tracking-and-history"></a>注文の追跡と履歴

[Store > **Order history] に** 移動すると、注文履歴を表示できます。これには、組織内のユーザーと他の管理者が行ったすべての注文が含まれます。 注文履歴には、注文の発送状態も含まれます。 注文の追跡、返品、または払い戻しに関する質問については、お問い合 UnifiedCommunications.com。 連絡先情報は、[注文履歴] ページで確認できます。

デバイス ストアに配置Teams、それに関連付けられているすべてのデータは、テナント注文とテナント データとして分類されます。

## <a name="provision-devices"></a>デバイスのプロビジョニング

リモート プロビジョニングをサポートするデバイスを購入すると、デバイスの出荷時に、それらのデバイスの MAC アドレスが Teams 管理センターに自動的に追加されます。 注文と出荷日によっては、MAC アドレスが管理センターの管理センターに表示Teams 5 日かかる場合があります。

デバイスが配信された後は、「デバイスを [リモートでプロビジョニング](remote-provision-remote-login.md#generate-a-verification-code) する」を参照して、プロビジョニングおよびサインイン プロセスを完了します。
