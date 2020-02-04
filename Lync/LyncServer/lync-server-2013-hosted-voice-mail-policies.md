---
title: 'Lync Server 2013: ホスト型ボイス メール ポリシー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f975868dad7bc0fcf6d5a2867ca2f3b81cd59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013 のホスト型ボイス メール ポリシー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

ホストされた*ボイスメールポリシー*は、ホストされた Exchange サービス上にあるメールボックスを持つユーザーの呼び出しをルーティングする場所について、Lync Server 2013 Exum ルーティングアプリケーションに情報を提供します。

<div>


> [!NOTE]  
> ホストされたボイスメールポリシーは、Lync Server 2013 でのホストされた Exchange UM との統合にのみ必要です。 オンプレミスの Exchange UM との統合には必要ありません。



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>ホストされたボイスメールポリシーのスコープ

ホストされたボイスメールポリシーのスコープによって、ポリシーが適用される階層レベルが決まります。 以下のスコープレベルで、ホストされたボイスメールポリシーを構成できます。

  - *グローバル*ポリシーは、Lync Server 2013 の展開におけるすべてのユーザーに影響を与える可能性があります。 ホストされた Exchange UM アクセスが有効になっていて、ユーザーごとのポリシーが割り当てられていない場合や、サイトポリシーがユーザーのサイトに割り当てられていない場合は、グローバルポリシーが適用されます。 グローバルポリシーは Lync Server 2013 と共にインストールされます。 必要に応じて変更できますが、名前の変更や削除はできません。

  - *サイト*ポリシーは、ポリシーが定義されているサイトをホームにしているすべてのユーザーに影響を与える可能性があります。 ユーザーがホストされた Exchange UM アクセス用に構成されていて、ユーザーごとのポリシーが割り当てられていない場合は、サイトポリシーが適用されます。

  - *ユーザーごと*のポリシーは、個々のユーザーまたはグループにのみ影響を与える可能性があります。 ユーザーごとのポリシーを適用するには、個々のユーザー、グループ、連絡先オブジェクトにポリシーを明示的に割り当てる必要があります。

<div>


> [!NOTE]  
> ほとんどの場合、ホストされるボイスメールのポリシーは1つだけ必要です。 多くの場合、すべてのニーズに合わせてグローバルポリシーを変更できます。 複数のホストされたボイスメールポリシーを展開する場合、そのようなすべてのポリシーにはユーザーごとのスコープがあります。



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>ホストされたボイスメールポリシーの属性

ボイスメールポリシーは、次の2つの属性を定義します。 Lync Server 2013 ExUM ルーティングアプリケーションは、ホストされた Exchange UM 実装に送信される INVITE メッセージの要求 URI に挿入します。

  - **Destination:** ホストされている Exchange UM サービスの完全修飾ドメイン名 (FQDN)。 この値は、ルーティング目的でオンプレミスの Lync Server Edge サーバーによって使用されます。
    
    <div>
    

    > [!NOTE]  
    > Exchange Online の FQDN は exap.um.outlook.com です。

    
    </div>

  - **組織:** Lync Server 2013 ユーザーのメールボックスをホームとする、ホストされた Exchange UM サービス上のテナントの FQDN。 ボイスメールのポリシーには、複数の組織を含めることができます。 ポリシーに複数の組織が含まれている場合、この属性は、Lync Server 2013 ユーザーメールボックスのホームとなる Exchange Server テナントのコンマ区切りリストである必要があります。

<div>


> [!NOTE]  
> ホストされた Exchange UM サービスのテナント管理者が、宛先と組織の属性設定に必要な値を提供します。 ポリシーを構成するには、CsHostedVoicemailPolicy コマンドレットを実行するか、CsHostedVoicemailPolicy コマンドレットを使用して存在するもの (グローバルポリシーなど) を変更する必要があります。



</div>

ホストされたボイスメールポリシーの管理について詳しくは、次のコマンドレットの Lync Server 管理シェルに関するドキュメントをご覧ください。

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>ユーザーごとのボイスメールポリシーの割り当て

ホストされたボイスメールのポリシーがユーザーごとのスコープで定義されている場合は、明示的に割り当てる必要があります。 CsHostedVoicemailPolicy コマンドレットを実行して、個々のユーザーまたはグループにポリシーを割り当てることができます。

ユーザーごとにホストされるボイスメールのポリシーの割り当てまたは削除の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

