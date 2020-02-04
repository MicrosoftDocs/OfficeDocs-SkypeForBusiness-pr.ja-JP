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
ms.openlocfilehash: 0125ff4719cd3dfeb65353df747395e596b45dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Lync Server 2013 での Lync と Skype の接続の有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-16_

プロビジョニング要求を送信した後は、Lync Server 環境と Lync-Skype の接続を構成するために必要な管理タスクに集中することができます。 このセクションでは、Lync Server の管理者が Lync Server を展開し、外部アクセスを構成していることを前提としています。 Lync Server の外部アクセスの構成の詳細については、「 [lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」および「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

Lync で lync を使用するための lync Server 環境を準備するには、Lync Server の管理者が次の3つの作業を完了している必要があります。

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. フェデレーションと PIC を構成する

組織内の Lync ユーザーと Skype ユーザーとの通信を可能にするには、フェデレーションが必要です。 パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されています。

![PIC の表示](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC の表示")

<div>


> [!IMPORTANT]  
> PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2 があります。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する

Lync Server コントロールパネルを使用して、管理者は、1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが社内の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。

![ポリシー](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "ポリシー")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Lync の Skype PIC プロバイダー設定を構成する

Lync Server 管理シェルを使用する場合、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。

<div>


> [!NOTE]  
> パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために、少なくとも1つのポリシー (この手順では、前の手順 2) を構成するまで、組織内の IM またはビデオ会議に参加することはできません。



</div>

1.  フェデレーションと PIC を構成するには、で[http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)「フェデレーションとパブリック IM 接続を有効または無効にする」を参照してください。

2.  フェデレーションさ[http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)れたユーザーアクセスをサポートするために、少なくとも1つのポリシーを構成するには、「パブリックユーザーアクセスを制御するためのポリシーの構成」を参照してください。

**既存の Messenger または Skype PIC プロバイダーを編集して、Skype 用に設定するには**

1.  Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  次の 2 つのコマンドを実行します。
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > 環境に PIC プロバイダーがなく、新しい PIC プロバイダーを作成している場合は、 <STRONG>CsPublicProvider</STRONG>コマンドレットを実行する必要はありません。

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 CU5 以降&amp; lync デスクトップクライアントに OFFICE 2013 SP1 で追加されました。 lync ユーザーが skype の連絡先を追加するには、Microsoft 以外のドメインを "装飾" して、skype (ユーザー (contoso) @msn の形式であることを確認し、ルーティングする必要があります。 こうした新しい設定により、ユーザーが [Skype 連絡先の追加] ダイアログ ボックスに入力したアドレスに NameDecorationExcludedDomainList のドメイン (現在は msn.com、live.com、Hotmail.com、outlook.com に対応できます) が含まれない場合は、このアドレスの NameDecorationRoutingDomain による自動書式設定 (msn.com に設定する必要があります) が可能になります。

    
    </div>

3.  Lync クライアントから、PIC プロバイダとして Skype を選択できるようになりました。 Skype クライアントを追加するには、お客様の Microsoft アカウントを指定します。 さらに、Microsoft アカウントで統合してログインした Skype ユーザーは、連絡先要求を Lync ユーザーに送信できます。 Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。 Lync にクライアントを追加する方法の詳細については、「lync を[使用したユーザーとしての Lync Server 2013 での lync の接続](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。
    
    ![Skype コンタクトを追加](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype コンタクトを追加")

4.  ホストさ[http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)れているプロバイダーの変更の詳細については、の「ホステッド SIP フェデレーションプロバイダーを作成または編集する」を参照してください。

これで、サーバー上で実行する必要がある管理タスクが完了します。 これで Lync と Skype の接続が設定されました。

</div>

</div>

<span> </span>

</div>

</div>

</div>

