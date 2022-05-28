---
title: デバイス ストアTeams
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
description: Teams管理センターのデバイス ストアでデバイスを参照して購入する方法について説明します
ms.openlocfilehash: da520b6396fa7e47288f4fdaa6b9f028ba16b3dd
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761449"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>Teams デバイス ストアでデバイスを購入する

>[!NOTE]
>Teams デバイス ストアは現在、**パブリック プレビュー** でのみ使用できます。 パブリック プレビューでは、今後の機能をテストし、フィードバックを提供できます。 パブリック プレビューに含まれる機能は完了していない可能性があり、変更が加えられる可能性があり、Office 365 Government Cloud ではサポートされていません。

Teams管理センターのデバイス ストアを使用すると、Microsoft Teamsの認定を受けたデバイスを参照、購入、プロビジョニングできます。  

 Teams管理センターのデバイス ストアを使用するには、[**デバイス > Microsoft Store]** に移動します。

## <a name="requirements"></a>要件

デバイス ストアを使用するには、グローバル管理者、Teams管理者、またはTeamsデバイス管理者である必要があります。

## <a name="browse-the-store"></a>ストアを参照する

デバイス ストアには、ヘッドセット、Web カメラ、Teams Rooms、デスク フォン、Teams ディスプレイなどのTeams デバイスなど、Teamsの認定を受けたすべてのデバイスが含まれます。 組織に必要なデバイスを見つけるために、並べ替え、フィルター処理、検索を行うことができます。

## <a name="purchase-devices"></a>デバイスを購入する

デバイス ストアからデバイスを購入すると、配送や配送を含む支払いとフルフィルメントは、Microsoft サード パーティのフルフィルメント パートナーである UnifiedCommunications.com によって処理されます。  

クレジット カードまたは発注書で支払うことができます。 発注書の支払いには、フルフィルメント プロバイダーとの 1 回限りのセットアップが必要です。

すべての注文は、配送後最大 30 日後に返すことができます。

## <a name="data-handling-and-sharing"></a>データの処理と共有

Teamsデバイス ストアは、Teams管理センターで購入を有効にするために、ユーザーとテナントの GUID を含む基本的なユーザーと会社の情報を UnifiedCommunications.com と共有する必要があります。

データ共有は既定で無効になっています。 有効にするには、Teamsデバイス ストアに移動し、設定アイコンを選択して設定をオンにします。  

この設定がオフの場合、データは共有されず、Teamsデバイス ストアを参照できますが、購入することはできません。 設定がオンの間に収集され、フルフィルメント プロバイダーと共有されたデータは、プライバシーに関する声明で指定されたとおりに処理されます。

## <a name="order-tracking-and-history"></a>注文の追跡と履歴

注文履歴を表示するには、[**注文履歴] Microsoft Store >** 移動します。これには、組織内の自分や他の管理者が行ったすべての注文が含まれます。 注文履歴には、注文の発送状態も含まれます。 注文の追跡、返品、または返金に関する質問については、UnifiedCommunications.com にお問い合わせください。 連絡先の情報は、[注文履歴] ページで確認できます。

Teams デバイス ストアに配置された注文とそれに関連付けられているすべてのデータは、テナントの注文とテナント データとして分類されます。

## <a name="provision-devices"></a>デバイスをプロビジョニングする

リモート プロビジョニングをサポートするデバイスを購入すると、デバイスの出荷時に、それらのデバイスの MAC アドレスがTeams管理センターに自動的に追加されます。 注文と出荷時によっては、MAC アドレスがTeams管理センターに表示されるまでに約 5 日かかる場合があります。

デバイスが配信されたら、デバイスを [リモートプロビジョニングしてプロビジョニング](remote-provision-remote-login.md#generate-a-verification-code) とサインインプロセスを完了する方法に関するページを参照してください。
