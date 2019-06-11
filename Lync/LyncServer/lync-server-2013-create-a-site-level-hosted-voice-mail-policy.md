---
title: 'Lync Server 2013: サイトレベルでホストされるボイスメールポリシーを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でサイトレベルでホストされるボイスメールのポリシーを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-24_

*サイト*ポリシーは、ポリシーが定義されているサイトをホームにしているすべてのユーザーに影響を与える可能性があります。 ユーザーがホストされた Exchange UM アクセス用に構成されていて、ユーザーごとのポリシーが割り当てられていない場合は、サイトポリシーが適用されます。 サイトポリシーを展開していない場合は、グローバルポリシーが適用されます。

サイトポリシーの構成の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - [新規-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a>サイトでホストされているボイスメールポリシーを作成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。 たとえば、以下を実行します。
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    この例では、サイトのスコープを持つホストされたボイスメールのポリシーを作成し、次のパラメーターを設定します。
    
      - **Id**は、スコープを含むポリシーの一意の識別子を指定します。 サイトスコープを持つポリシーの場合、id パラメーター値は形式`site:` * \<名\>* で指定する必要があります。 `site:Redmond`たとえば、などです。
    
      - [ **Destination** ] は、ホストされた Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。 このパラメーターは省略可能ですが、ホストされたボイスメールに対してユーザーを有効にしようとしても、ユーザーに割り当てられているポリシーに送信先の値がない場合、有効にすることはできません。
    
      - **説明**ポリシーに関するオプションの説明情報を提供します。
    
      - [**組織**] は、Lync Server 2013 のホームユーザーである Exchange テナントのコンマ区切りリストを指定します。 各テナントは、ホストされた Exchange UM サービスでそのテナントの FQDN として指定する必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

