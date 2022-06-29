---
title: Teams デバイス ストア
ms.author: dstrome
author: dstrome
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
description: Teams 管理センターのデバイス ストアでデバイスを参照して購入する方法について説明します
ms.openlocfilehash: 9e555cd0f389c8158e66b824183a1038fc11ce04
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240716"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>Teams デバイス ストアでデバイスを購入する

Teams 管理センターのデバイス ストアを使用すると、Microsoft Teams の認定を受けたデバイスを参照、購入、プロビジョニングできます。  

 Teams 管理センターでデバイス ストアを使用するには、 **デバイス > ストア** に移動します。

## <a name="requirements"></a>要件

デバイス ストアを使用するには、グローバル管理者または Teams 管理者である必要があります。

## <a name="browse-the-store"></a>ストアを参照する

デバイス ストアには、ヘッドセット、Web カメラ、Teams Rooms、デスクフォン、Teams ディスプレイなどの Teams デバイスを含む、Teams 向けに認定されたすべてのデバイスが含まれます。 組織に必要なデバイスを見つけるために、並べ替え、フィルター処理、検索を行うことができます。

## <a name="purchase-devices"></a>デバイスを購入する

デバイス ストアからデバイスを購入すると、配送や配送を含む支払いとフルフィルメントは、Microsoft サード パーティのフルフィルメント パートナーである UnifiedCommunications.com によって処理されます。  

クレジット カードまたは発注書で支払うことができます。 発注書の支払いには、フルフィルメント プロバイダーとの 1 回限りのセットアップが必要です。

すべての注文は、配送後最大 30 日後に返すことができます。

## <a name="data-handling-and-sharing"></a>データの処理と共有

Teams デバイス ストアは、Teams 管理センターで購入を有効にするために、ユーザーとテナントの GUID を含む基本的なユーザーと会社の情報を UnifiedCommunications.com と共有する必要があります。

データ共有は既定で無効になっています。 これを有効にするには、Teams デバイス ストアに移動し、設定アイコンを選択して設定をオンにします。  

この設定がオフの場合、データは共有されず、Teams デバイス ストアを参照できますが、購入することはできません。 設定がオンの間に収集され、フルフィルメント プロバイダーと共有されたデータは、プライバシーに関する声明で指定されたとおりに処理されます。

## <a name="order-tracking-and-history"></a>注文の追跡と履歴

注文履歴を表示するには、[ **ストア >注文履歴**] に移動します。これには、自分と組織内の他の管理者が行ったすべての注文が含まれます。 注文履歴には、注文の発送状態も含まれます。 注文の追跡、返品、または返金に関する質問については、UnifiedCommunications.com にお問い合わせください。 連絡先の情報は、[注文履歴] ページで確認できます。

Teams デバイス ストアに配置された注文とそれに関連付けられているすべてのデータは、テナント注文とテナント データとして分類されます。

## <a name="provision-devices"></a>デバイスをプロビジョニングする

リモート プロビジョニングをサポートするデバイスを購入すると、デバイスの出荷時に、それらのデバイスの MAC アドレスが Teams 管理センターに自動的に追加されます。 注文と出荷時によっては、MAC アドレスが Teams 管理センターに表示されるまでに約 5 日かかる場合があります。

デバイスが配信されたら、デバイスを [リモートプロビジョニングしてプロビジョニング](remote-provision-remote-login.md#generate-a-verification-code) とサインインプロセスを完了する方法に関するページを参照してください。
