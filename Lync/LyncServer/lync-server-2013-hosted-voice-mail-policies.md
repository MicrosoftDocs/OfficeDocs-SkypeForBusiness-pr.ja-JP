---
title: 'Lync Server 2013: ホストボイスメールポリシー'
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
ms.openlocfilehash: 01e844e62934a697b12afa76d2e9c9405a30a4a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013 のホストボイスメールポリシー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

*ホストボイスメールポリシー*は、ホストされた Exchange サービスにメールボックスがあるユーザーの呼び出しをルーティングする場所について、Lync Server 2013 Exum ルーティングアプリケーションに情報を提供します。

<div>


> [!NOTE]  
> ホストボイスメールポリシーは、ホストされた Exchange UM との Lync Server 2013 の統合にのみ必要です。 内部設置型の Exchange UM との統合には必要ありません。



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>ホスト ボイス メール ポリシーのスコープ

ホスト ボイス メール ポリシーのスコープでは、ポリシーが適用される階層レベルが指定されます。以下のスコープ レベルのホスト ボイス メール ポリシーを構成できます。

  - *グローバル*ポリシーは、Lync Server 2013 展開内のすべてのユーザーに影響を与える可能性があります。 Hosted Exchange UM へのアクセスが有効になっているユーザーに対してユーザー単位のポリシーが割り当てられていない場合、およびユーザーのサイトにサイト ポリシーが割り当てられていない場合には、グローバル ポーリシーが適用されます。 グローバルポリシーは、Lync Server 2013 と共にインストールされます。 グローバル ポリシーを必要に応じて変更することはできますが、名前変更や削除はできません。

  - *サイト* ポリシーは、このポリシーが定義されているサイトに所属するすべてのユーザーに影響します。Hosted Exchange UM にアクセスできるように構成されているユーザーにユーザー単位のポリシーが割り当てられていない場合には、サイト ポリシーが適用されます。

  - *ユーザー単位の*ポリシーは、個々のユーザーやグループにだけ影響します。ユーザー単位のポリシーを適用するには、個々のユーザー、グループ、または連絡先オブジェクトにこのポリシーを明示的に割り当てる必要があります。

<div>


> [!NOTE]  
> ほとんどの場合には、必要なホスト ボイス メール ポリシーは 1 つだけです。多くの場合には、必要に応じてグローバル ポリシーを変更できます。複数のホスト ボイス メール ポリシーを展開する場合には、展開するすべてのポリシーにユーザー単位のスコープがあります。



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>ホスト ボイス メール ポリシーの属性

ボイスメールポリシーは、Lync Server 2013 ExUM ルーティングアプリケーションが、hosted Exchange UM 実装に送信される INVITE メッセージの要求 URI に挿入する2つの属性を定義します。

  - **Destination:** Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN)。 この値は、ルーティングのためにオンプレミスの Lync Server エッジサーバーによって使用されます。
    
    <div>
    

    > [!NOTE]  
    > Exchange Online の FQDN は exap.um.outlook.com です。

    
    </div>

  - **組織:** Lync Server 2013 ユーザーのメールボックスをホームとする、ホストされた Exchange UM サービス上のテナントの FQDN。 ボイス メール ポリシーには複数の組織が含まれていることがあります。 ポリシーに複数の組織が含まれている場合、この属性は、Lync Server 2013 ユーザーメールボックスのホームとなる Exchange Server テナントのコンマ区切りのリストである必要があります。

<div>


> [!NOTE]  
> Hosted Exchange UM サービスのテナント管理者が、宛先と組織の属性設定に必要な値を提供します。ポリシーを構成するには、New-CsHostedVoicemailPolicy コマンドレットを実行するか、または Set-CsHostedVoicemailPolicy コマンドレットを使用して既存のポリシー (例: グローバル ポリシー) を変更する必要があります。



</div>

ホストボイスメールポリシーの管理の詳細については、「Lync Server Management Shell」のドキュメントの次のコマンドレットを参照してください。

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>ユーザー単位のボイス メール ポリシーの割り当て

ホスト ボイス メール ポリシーがユーザー単位のスコープで定義されている場合には、ユーザー単位のスコープを明示的に割り当てる必要があります。Grant-CsHostedVoicemailPolicy コマンドレッドを実行して、ポリシーを個々のユーザーまたはグループに割り当てることができます。

ユーザーごとのホストボイスメールポリシーの割り当てまたは削除の詳細については、「Lync Server Management Shell」のドキュメントの次のコマンドレットを参照してください。

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

