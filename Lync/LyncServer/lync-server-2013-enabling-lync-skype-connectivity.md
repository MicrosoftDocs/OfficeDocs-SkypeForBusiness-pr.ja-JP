---
title: 'Lync Server 2013: Lync と Skype の接続の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb14153739c5f29e88044eae89a1322b046a0a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Lync Server 2013 での Lync と Skype の接続の有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-16_

プロビジョニング要求を送信した後で、lync Server 環境と Lync-Skype 接続を構成するために必要な管理タスクに集中することができます。 このセクションでは、Lync server 管理者が Lync Server を展開し、外部アクセスを構成したと仮定します。 Lync Server の外部アクセスの構成の詳細については、「lync server [2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

Lync server 環境で Lync と Skype の接続を準備するには、Lync Server 管理者が次の3つのタスクを完了する必要があります。

<div>

## <a name="1-configure-federation-and-pic"></a>1\. フェデレーションと PIC を構成する

Skype ユーザーが組織内の Lync ユーザーと通信できるようにするには、フェデレーションが必要です。 パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されます。

![PIC の表示](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC の表示")

<div>


> [!IMPORTANT]  
> PIC フェデレーションは、Live Communications Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成する

Lync Server コントロールパネルを使用すると、管理者は1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。

![ポリシー](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "ポリシー")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Lync の Skype PIC プロバイダー設定を構成する

Lync Server 管理シェルを使用して、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。

<div>


> [!NOTE]  
> パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために少なくとも1つのポリシー (この手順の前の手順 2) を構成するまで、組織内の IM またはオーディオまたはビデオ会議に参加できません。



</div>

1.  フェデレーションと PIC を構成するには、「」の「フェデレーションとパブリック IM 接続[https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063)を有効または無効にする」を参照してください。

2.  フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成するには、「」 [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064)の「パブリックユーザーアクセスを制御するようにポリシーを構成する」を参照してください。

**既存の Messenger または Skype PIC プロバイダーを編集して Skype 用に構成するには**

1.  Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  次の2つのコマンドを実行します。
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > 環境に PIC プロバイダがなく、新しい PIC プロバイダを作成している場合は、 <STRONG>enable-cspublicprovider</STRONG>コマンドレットを実行する必要はありません。

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 CU5 &amp; lync desktop Client in OFFICE 2013 SP1 では、NameDecorationRoutingDomain と NameDecorationExcludedDomainList は、lync ユーザーが skype の連絡先を追加することによって、Microsoft 以外 @msn のドメインを識別して skype 形式にルーティングする必要がある状況を改善しました ()。 これらの新しい設定では、NameDecorationRoutingDomain (msn.com に設定する必要があります) の [Skype 連絡先の追加] ダイアログボックスで、ユーザーの入力を自動的に書式設定することができます (NameDecorationExcludedDomainList 内のドメインが含まれていない場合)。現時点では、msn.com、live.com、Hotmail.com、outlook.com) をサポートできます。

    
    </div>

3.  Lync クライアントから、PIC プロバイダーとして Skype を選択し、Microsoft アカウントを指定して Skype クライアントを追加できるようになりました。 また、Microsoft アカウントを使用して合併およびログインした Skype ユーザーは、Lync ユーザーに対して連絡先要求を送信できます。 Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。 Lync にクライアントを追加する方法の詳細については、「lync [Server 2013 でのエンドユーザーとしての lync 接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。
    
    ![Skype 連絡先を追加する](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype 連絡先を追加する")

4.  ホストされるプロバイダーの変更の詳細については、「」の「ホストさ[https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)れた SIP フェデレーションプロバイダーを作成または編集する」を参照してください。

これで、サーバー上で実行する必要のある管理タスクが完了します。 これで、Lync と Skype の接続が設定されました。

</div>

</div>

<span> </span>

</div>

</div>

</div>

