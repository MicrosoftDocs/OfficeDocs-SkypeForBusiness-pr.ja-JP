---
title: Lync Server パブリック IM 接続プロビジョニングサイトへのアクセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e57bac3460c8feb5b3417f433aa228825d824a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529754"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Lync server 2013 からの Lync Server パブリック IM 接続プロビジョニングサイトへのアクセス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2019-03-22_

以前の PIC プロビジョニング方法と比較して、Lync-Skype 接続のプロビジョニングプロセスが変更されました。 このプロビジョニングプロセスは、完了するまでに最大で30日間かかることがあります。 このドキュメントの残りの手順を完了する前に、このプロセスを最初に開始することをお勧めします。 アカウントの Lync-Skype プロビジョニングプロセスが完了すると、アカウントがアクティブ化され、対象ユーザーのパブリック IM 接続が有効になります。

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Lync-Skype 接続をプロビジョニングするには、次の情報が必要です。

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 契約番号</p></li>
<li><p>アクセスエッジサービスの完全修飾ドメイン名 (FQDN)</p></li>
<li><p>セッション開始プロトコル (SIP) ドメイン</p></li>
<li><p>追加のアクセスエッジサービスの Fqdn</p></li>
<li><p>連絡先情報</p></li>
</ol></td>
</tr>
</tbody>
</table>

2019年4月から、pic.lync.com web サイトを介して Skype フェデレーションを準備されているお客様の連絡先情報の収集と保存を停止します。 この変更は、pic.lync.com プロビジョニングシステムが Microsoft プライバシーポリシーに準拠していることを確認するために行われます。 

この変更が有効になると、保留中のプロビジョニング変更に対する電子メール更新を提供することができなくなります。 PIC プロビジョニングの変更は、通常、入力されてから24-48 時間以内に完了します。 準備要求の提出後、Skype フェデレーションの問題が依然として48時間発生している場合は、さらに詳しく調査するために Microsoft テクニカルサポートにご協力ください。

> [!IMPORTANT]
> この変更の一環として、以前に入力したすべての連絡先情報は、2019年4月の終了後にシステムから削除されます。

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Lync-Skype 接続のプロビジョニングプロセスを開始するには、次の操作を行います。

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><strong>https://pic.lync.com</strong>Microsoft Windows LIVE ID を使用して、web サイトにサインインします。</p></li>
<li><p>[Microsoft ライセンス契約の種類] を選択します。</p></li>
<li><p>このチェックボックスをオンにして、Lync Server の製品使用権を読んで同意していることを確認します。</p></li>
<li><p>[ <strong>プロビジョニング要求を開始</strong> する] ページで、適切なリンクをクリックしてプロビジョニング要求を開始します。</p></li>
<li><p>[ <strong>プロビジョニング情報の指定</strong> ] ページで、 <strong>アクセスエッジサービスの FQDN</strong>を入力します。 たとえば、 <strong>sip.contoso.com</strong>のようになります。</p>



> [!IMPORTANT]
> 2017年7月1日以降、Microsoft は、パブリック IM 接続用に展開されたフェデレーション DNS SRV レコードを使用して引き続き作業を行う必要があります。

</li>
<li><p>少なくとも1つの SIP ドメイン名を入力し、[ <strong>追加</strong>] をクリックします。</p>



> [!IMPORTANT]
> プロビジョニングプロセスを完了するには、少なくとも1つのアクセスエッジサーバーと1つの SIP ドメインが必要です。 SIP ドメインとアクセスエッジサーバーが、ネットワーク上でアクティブで、機能していて、到達可能である必要があります。

</li>
<li><p><strong>パブリック IM サービスプロバイダー</strong>の一覧で、[ <strong>Skype]</strong>を選択し、[<strong>次</strong>へ] をクリックして連絡先情報を追加し、プロビジョニング要求を送信します。</p></li>
</ol></td>
</tr>
</tbody>
</table>


プロビジョニング要求を送信した後は、アカウントがアクティブ化され、ユーザーがパブリック IM 接続を有効にするには、最大で30日かかることがあります。

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>フェデレーションとパブリック IM 接続の有効化 (PIC)

プロビジョニング要求を送信した後は、Lync Server 環境および Lync-Skype 接続を構成するために必要な管理タスクに集中できます。 このセクションでは、Lync server 管理者が Lync Server を展開し、外部アクセスを構成したと仮定します。 Lync Server の外部アクセスの構成の詳細については、「」の「外部ユーザーアクセスを計画する」 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) と「外部ユーザーアクセスを展開する」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) 。

Lync server 環境で Lync-Skype 接続を準備するには、Lync Server 管理者が次の3つのタスクを完了する必要があります。

<div>

## <a name="1-configure-federation-and-pic"></a>1\. フェデレーションと PIC を構成する

Skype ユーザーが組織内の Lync ユーザーと通信できるようにするには、フェデレーションが必要です。 パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されます。

<div>


> [!IMPORTANT]
> PIC フェデレーションは、Live Communications Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成する

Lync Server コントロールパネルを使用すると、管理者は1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Lync の Skype PIC プロバイダー設定を構成する

Lync Server 管理シェルを使用して、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。

<div>


> [!NOTE]
> パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために、少なくとも1つのポリシー (この手順の手順 2) を構成するまで、組織内の IM または会議に参加できません。<BR>フェデレーションと PIC を構成するには、「」の「フェデレーションとパブリック IM 接続を有効または無効にする」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> 。<BR>フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成するには、「」の「パブリックユーザーアクセスを制御するようにポリシーを構成する」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> 。



</div>

1.  Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  次の2つのコマンドを実行します。
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > 環境に PIC プロバイダがなく、新しい PIC プロバイダを作成している場合は、 <STRONG>enable-cspublicprovider</STRONG> コマンドレットを実行する必要はありません。

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Lync Server 2013 CU5 &amp; lync desktop client In Office 2013 SP1 では、NameDecorationRoutingDomain と NameDecorationExcludedDomainList は、lync ユーザーが skype の連絡先を追加することによって、Microsoft 以外 @msn のドメインを識別して skype 形式にルーティングする必要がある状況を改善しました ()。 これらの新しい設定によって、NameDecorationRoutingDomain (現在は msn.com、live.com、Hotmail.com、outlook.com) のドメインが含まれていない場合は、[Skype 連絡先の追加] ダイアログボックスの [Skype 連絡先の追加] ダイアログボックスで、ユーザーの入力を自動書式設定することができます (msn.com に設定する必要があります)。

        
        </div>

3.  Lync クライアントから、PIC プロバイダーとして Skype を選択し、Microsoft アカウントを指定して Skype クライアントを追加できるようになりました。 また、Microsoft アカウントを使用して合併およびログインした Skype ユーザーは、Lync ユーザーに対して連絡先要求を送信できます。 Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。 Lync にクライアントを追加する方法の詳細については、「 [Lync Server 2013 でのエンドユーザーとしての Lync-Skype 接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。

4.  ホストされるプロバイダーの変更の詳細については、「」の「ホストされた SIP フェデレーションプロバイダーを作成または編集する」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。

これで、サーバー上で実行する必要のある管理タスクが完了します。 これで Lync-Skype 接続がセットアップされます。

</div>

</div>

<div>

## <a name="additional-resources"></a>その他のリソース

[エンドユーザーとしての Lync Server 2013 での Lync-Skype 接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Lync Server 2013 での Lync-Skype 接続のプロビジョニングガイド](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

