---
title: 'Lync Server 2013: ダイヤルイン会議のダイヤルプランを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4178d443d8577a9a141cbdd5bbeee05856ae6b40
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504764"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-25_

ダイヤルイン会議を展開するときは、ダイヤルインのアクセス電話番号をルーティングするために、1 つ以上のダイヤル プランを作成または変更する必要があります。 各ダイヤル プランの少なくとも 1 つの正規化ルールにより、内線電話番号が E.164 形式の完全な電話番号に変換されることを確認してください。ダイヤルイン会議のユーザーは、自分の暗証番号 (PIN) と電話番号を入力して、認証済みのエンタープライズ ユーザーとして会議に参加します。 内線番号を完全な電話番号に変換する正規化ルールが必要なのは、内線番号だけの入力でユーザーを認証できるようにするためです。

ダイヤルイン会議のダイヤル プランをセットアップするには、次の作業を行います。

  - エンタープライズ Voip を展開するかどうかにかかわらず、グローバルダイヤルプランを変更してダイヤルイン会議の地域を追加し、ダイヤルインアクセス番号を正規化ルールに正確に変換するようにします。 詳細な手順については、「 [Modify a dial plan In Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)」を参照してください。

  - エンタープライズ Voip を展開しなかった場合は、ダイヤルイン会議アクセス番号のダイヤルプランを作成します。 ダイヤルイン会議の地域を忘れないようにしてください。 詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)」を参照してください。

  - エンタープライズ Voip を展開した場合は、必要に応じて、地域を含め、ダイヤルインアクセス番号に適切な正規化ルールを使用するようにエンタープライズ Voip ダイヤルプランを変更します。 詳細な手順については、「 [Modify a dial plan In Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)」を参照してください。 また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。 詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)」を参照してください。

地域の計画の詳細については、「計画」のドキュメントの「 [Lync Server 2013 のダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md) 」を参照してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのダイヤルプラン情報の表示](lync-server-2013-view-dial-plan-information.md)

  - [Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)

  - [Lync Server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)

  - [Lync Server 2013 での正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

