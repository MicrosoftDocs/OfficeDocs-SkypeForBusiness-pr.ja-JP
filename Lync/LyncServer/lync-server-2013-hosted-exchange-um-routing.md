---
title: 'Lync Server 2013: Hosted Exchange UM ルーティング'
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
ms.openlocfilehash: 57efdcebe52f9b32f30c22ebcbf107d3cd9d8a7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a>Lync Server 2013 での Hosted Exchange UM ルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

Exchange UM ルーティングアプリケーションは、フロントエンドサーバー上で実行され、オンプレミスの Microsoft Exchange Server ユニファイドメッセージング (UM) 展開または hosted Exchange UM サービスに呼び出しをルーティングします。

<div>

## <a name="the-exum-routing-application"></a>ExUM ルーティング アプリケーション

Lync Server 2013 Exchange UM ルーティングアプリケーションは、次の図に示すように、ユーザーアカウント設定およびホストボイスメールポリシーパラメーターから情報を使用して、ホストされているボイスメッセージングの呼び出しをルーティングする方法を決定します。

**Exchange UM ルーティングが混在している展開の例**

![オンプレミスの Lync Server Exchange UM 展開](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "オンプレミスの Lync Server Exchange UM 展開")

Exchange UM ルーティングは、オンプレミスの Exchange UM に対して有効になっているユーザー、またはホストされた Exchange UM が有効になっているユーザー、またはその2つの組み合わせに対して、呼び出しをルーティングするように構成できます。

たとえば、Roy のメールボックスと Exchange UM サービスがオンプレミスの Exchange 展開に所属しているとします。

  - Roy のユーザーアカウントからのプロキシアドレス情報は、ExUM ルーティングアプリケーションが、その呼び出しを社内 Exchange UM サーバーにルーティングするために使用する情報を提供します。

Alice のメールボックスと Exchange UM サービスは、hosted Exchange サービスプロバイダーのデータセンターにあります。 自分の Exchange UM 呼び出しのルーティングは、次のように構成されます。

  - Alice のユーザー アカウントの msExchUCVoiceMailSettings 属性に設定された値は、ExUM ルーティング アプリケーションに対して、ホスト ボイス メール ポリシーのルーティング情報を確認するように示しています。
    
    <div>
    

    > [!NOTE]  
    > MsExchUCVoiceMailSettings 属性の値は、Exchange サービスプロバイダーまたは Lync Server 2013 のいずれかの管理者が設定できます。 前の図に示した例では、値 (CsHostedVoiceMail = 1) が Lync Server 2013 管理者によって設定され、Alice のホストボイスメールを有効にしました。 この属性の詳細については、「 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 の Hosted Exchange user management</A>」を参照してください。

    
    </div>

  - Alice のユーザー アカウントに割り当てられたホスト ボイス メール ポリシーは、次のルーティング情報を提供します。
    
      - Destination は hosted Exchange UM サービスプロバイダー (ls.ExUm.\<この例では、\>この例では、hostedexchangeserver.)。
    
      - 組織は、ls にある Exchange Server テナントの SIP メッセージのルーティング Fqdn であるテナント Id で識別されます。ExUm.\<この例では、corp.contoso.com と corp.litwareinc.com を有効にし\>ます。
        
        <div>
        

        > [!NOTE]  
        > Exchange Online の FQDN は exap.um.outlook.com です。

        
        </div>
        
        詳細については、「 [Lync Server 2013 のホストボイスメールポリシー](lync-server-2013-hosted-voice-mail-policies.md)」を参照してください。

<div>


> [!NOTE]  
> msExchUCVoiceMailSettings 属性と UM プロキシ アドレス設定の両方がユーザー アカウントに設定されている場合、msExchUCVoiceMailSettings 属性が優先されます。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

