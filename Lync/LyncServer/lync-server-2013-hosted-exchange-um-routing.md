---
title: 'Lync Server 2013: Hosted Exchange UM のルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e04198813f7bb0647671dbb23e12889b108ee846
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013 Hosted Exchange UM のルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

Exchange UM ルーティングアプリケーションは、オンプレミスの Microsoft Exchange Server ユニファイドメッセージング (UM) 展開またはホストされた Exchange UM サービスのいずれかに、通話をルーティングするために、フロントエンドサーバー上で実行されます。

<div>

## <a name="the-exum-routing-application"></a>ExUM ルーティングアプリケーション

Lync Server 2013 Exchange UM ルーティングアプリケーションでは、次の図に示すように、ユーザーアカウントの設定とホストされたボイスメールポリシーのパラメーターから情報を使って、ホストされている音声メッセージの着信をルーティングする方法を決定します。

**混在展開の Exchange UM ルーティングの例**

![オンプレミスの Lync Server Exchange UM の展開](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "オンプレミスの Lync Server Exchange UM の展開")

Exchange UM ルーティングは、オンプレミスの Exchange UM を有効にしているユーザー、またはホストされている Exchange UM を有効にしているユーザー、またはこの2つの組み合わせに対して、着信をルーティングするように構成できます。

たとえば、Roy のメールボックスと Exchange UM サービスがオンプレミスの Exchange 展開のホームにあるとします。

  - Roy のユーザーアカウントからのプロキシアドレス情報は、ExUM ルーティングアプリケーションがオンプレミスの Exchange UM サーバーへの呼び出しをルーティングするために使用する情報を提供します。

アリスのメールボックスと Exchange UM サービスは、ホスティングされている Exchange サービスプロバイダーのデータセンターにあります。 Exchange UM の呼び出しに対するルーティングは、次のように構成されます。

  - Alice のユーザーアカウントの msExchUCVoiceMailSettings 属性で設定された値は、ExUM ルーティングアプリケーションに対して、ホストされたボイスメールポリシーでルーティングの詳細を確認するように指示します。
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 属性の値は、Exchange サービスプロバイダーまたは Lync Server 2013 管理者のいずれかで設定できます。 上の図の例では、Lync Server 2013 管理者によって、ホストされたボイスメールを有効にするように値 (CsHostedVoiceMail = 1) が設定されていました。 この属性の詳細については、「 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 でのホスト型 Exchange ユーザーの管理</A>」を参照してください。

    
    </div>

  - Alice のユーザーアカウントに割り当てられているホスト型ボイスメールのポリシーによって、ルーティングの詳細が提供されます。
    
      - [Destination] は、ホストされている Exchange UM サービスプロバイダーです (ls)。ExUm。\<この例では、\>hostedexchangeserver を使用しています)。
    
      - 組織は、ls に配置されている Exchange Server テナントの SIP メッセージのルーティング Fqdn であるテナント Id によって識別されます。ExUm。\<この例では、corp.contoso.com と corp.litwareinc.com を使用し\>ます。
        
        <div>
        

        > [!NOTE]  
        > Exchange Online の FQDN は exap.um.outlook.com です。

        
        </div>
        
        詳細については、「 [Lync Server 2013 のホスト型ボイスメールポリシー](lync-server-2013-hosted-voice-mail-policies.md)」を参照してください。

<div>


> [!NOTE]  
> ユーザーアカウントに msExchUCVoiceMailSettings 属性と UM プロキシアドレスの両方の設定が含まれている場合は、msExchUCVoiceMailSettings 属性が優先されます。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

