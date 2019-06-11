---
title: 'Lync Server 2013: ダイヤルイン会議のダイヤル プランの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11424148db609fa8225b6c98d1de52fa360eb044
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-25_

ダイヤルイン会議を展開するときに、ダイヤルインアクセス用電話番号をルーティングするための1つ以上のダイヤルプランを作成または変更する必要があります。 各ダイヤルプランの少なくとも1つの正規化ルールによって、電話の内線番号が E.i 形式で完全な電話番号に変換されていることを確認してください。 ダイヤルイン会議のユーザーは、自らの暗証番号 (PIN) と電話番号を入力することで、認証されたエンタープライズ ユーザーとして会議に参加します。 内線番号を総合的な電話番号に変化する正規化ルールを管理者が定義する必要があり、その結果、ユーザーは内線番号のみを入力したときに認証を受けることができます。

ダイヤルイン会議のダイヤルプランをセットアップするには、次の操作を行います。

  - エンタープライズ VoIP を展開するかどうかに関係なく、グローバル ダイヤル プランを変更して、ダイヤルイン会議の地域を追加し、正規化ルールによりダイヤルイン アクセス番号が正確に変換されることを確認します。 詳細な手順については、「 [Lync Server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)」を参照してください。

  - エンタープライズ VoIP が展開されていない場合は、ダイヤルイン会議のアクセス電話番号に対応するダイヤル プランを作成します。 ダイヤルイン会議の地域を忘れないようにしてください。 詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください。

  - エンタープライズ VoIP が展開されている場合は、必要に応じてエンタープライズ VoIP を変更して地域を含め、ダイヤルイン アクセス番号のための適切な正規化ルールを使用します。 詳細な手順については、「 [Lync Server 2013 でダイヤルプランを変更する](lync-server-2013-modify-a-dial-plan.md)」を参照してください。 また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。 詳細な手順については、「 [Lync Server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」を参照してください。

計画地域の詳細については、計画ドキュメントの「 [Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのダイヤルプラン情報の表示](lync-server-2013-view-dial-plan-information.md)

  - [Lync Server 2013 でダイヤルプランを作成する](lync-server-2013-create-a-dial-plan.md)

  - [Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)

  - [Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

