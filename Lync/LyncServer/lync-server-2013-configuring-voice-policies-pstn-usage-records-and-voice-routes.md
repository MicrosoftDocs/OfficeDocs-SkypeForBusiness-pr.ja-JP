---
title: 音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3a87063503d373c8ef318633c5113624fef00b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a>Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-10_

音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。

新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。

<div>


> [!NOTE]
> <EM>ユーザー スコープ</EM>を使用して音声ポリシーを作成し、それを個々のユーザーまたはグループに割り当てることもできます。



</div>

これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Lync Server 2013 での PSTN 使用状況レコードの表示](lync-server-2013-view-pstn-usage-records.md)

  - [Lync Server 2013 での発信通話用のボイス ルートの構成](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Lync Server 2013 での音声ルーティング構成のエクスポートとインポート](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

