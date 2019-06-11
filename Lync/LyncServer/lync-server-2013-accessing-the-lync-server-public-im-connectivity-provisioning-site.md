---
title: Lync Server パブリック IM 接続プロビジョニング サイトへのアクセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6e028afcd3a9affc6c316b7cb373e124e6d5b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Lync Server 2013 から Lync Server パブリック IM 接続プロビジョニング サイトへのアクセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2019-03-22_

以前の PIC プロビジョニング方法と比較して、Lync のプロビジョニングプロセスが変更されました。 このプロビジョニングプロセスは、完了までに最大で30日間かかることがあります。 Microsoft は、このドキュメントの残りの手順を完了する前に、このプロセスを先に開始することをお勧めします。 アカウントの Lync-Skype プロビジョニングプロセスが完了すると、アカウントが有効になり、有効なユーザーにパブリック IM 接続が有効になります。

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Lync と Skype の接続をプロビジョニングするには、次の情報が必要です。

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 契約番号</p></li>
<li><p>アクセス エッジ サービスの完全修飾ドメイン名 (FQDN)</p></li>
<li><p>セッション開始プロトコル (SIP) のドメイン</p></li>
<li><p>追加のアクセス エッジ サービスの FQDN</p></li>
<li><p>連絡先情報</p></li>
</ol></td>
</tr>
</tbody>
</table>

2019年4月以降、pic.lync.com の web サイトから Skype フェデレーションを提供されているお客様の連絡先情報の収集と保持を停止します。 この変更は、pic.lync.com プロビジョニングシステムが Microsoft のプライバシーポリシーに準拠していることを確認するために行われています。 

この変更が有効になった後は、保留中のプロビジョニングの変更でメールの更新を提供することはできなくなります。 PIC プロビジョニングの変更は、通常、入力後の24-48 時間以内に完了します。 引き続き Skype フェデレーションの問題が発生した場合は、プロビジョニングリクエストの送信後に48時間がかかる場合は、Microsoft テクニカルサポートに協力して、さらに詳しく調査してください。

> [!IMPORTANT]
> この変更の一環として、以前に入力したすべての連絡先情報は、2019年4月のによってシステムから削除されます。

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Lync のプロビジョニングプロセスを開始するには、次の手順を実行します。

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft Windows Live ID を使用<strong>https://pic.lync.com</strong>して、web サイトにサインインします。</p></li>
<li><p>Microsoft ライセンスの契約の種類を選びます。</p></li>
<li><p>このチェックボックスをオンにして、Lync Server の製品使用権限を読み、同意していることを確認します。</p></li>
<li><p>[<strong>プロビジョニング要求の開始</strong>] ページで、適切なリンクをクリックしてプロビジョニング要求を開始します。</p></li>
<li><p>[<strong>プロビジョニング情報の指定</strong>] ページで、<strong>アクセスエッジサービスの FQDN</strong>を入力します。 たとえば、 <strong>sip.contoso.com</strong>のようになります。</p>



> [!IMPORTANT]
> 2017年7月1日以降、お客様には、引き続き機能するために、Microsoft がパブリック IM 接続用に展開されたフェデレーション DNS SRV レコードを追加する必要があります。

</li>
<li><p>少なくとも1つ以上の SIP ドメイン名を入力して、「<strong>追加</strong>」をクリックします。</p>



> [!IMPORTANT]
> プロビジョニング処理を完了するには、少なくとも1つのアクセスエッジサーバーと1つの SIP ドメインが必要です。 SIP ドメインとアクセス エッジ サーバーは、アクティブで、正常に機能し、ネットワーク上で到達可能である必要があります。

</li>
<li><p><strong>パブリック IM サービスプロバイダ</strong>のリストで、「 <strong>Skype</strong> 」を選択し、「<strong>次</strong>へ」をクリックして連絡先情報を追加し、プロビジョニングリクエストを送信します。</p></li>
</ol></td>
</tr>
</tbody>
</table>


プロビジョニング要求が送信されると、アカウントがアクティブ化され、ユーザーがパブリック IM 接続を有効にするまでに最長で30日間かかることがあります。

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>フェデレーションとパブリック IM 接続 (PIC) の有効化

プロビジョニング要求を送信した後は、Lync Server 環境と Lync-Skype の接続を構成するために必要な管理タスクに集中することができます。 このセクションでは、Lync Server の管理者が Lync Server を展開し、外部アクセスを構成していることを前提としています。 Lync Server の外部アクセスの構成の詳細については、「」 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772)および「外部ユーザーアクセスの計画」を参照して[https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)ください。

Lync で lync を使用するための lync Server 環境を準備するには、Lync Server の管理者が次の3つの作業を完了している必要があります。

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. フェデレーションと PIC を構成する

組織内の Lync ユーザーと Skype ユーザーとの通信を可能にするには、フェデレーションが必要です。 パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Lync ユーザーが Skype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、次に示す Lync Server コントロールパネルを使用して構成されています。

<div>


> [!IMPORTANT]
> PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2 があります。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する

Lync Server コントロールパネルを使用して、管理者は、1つ以上の外部ユーザーアクセスポリシーを構成して、Skype ユーザーが社内の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Lync の Skype PIC プロバイダー設定を構成する

Lync Server 管理シェルを使用する場合、管理者は Lync クライアントポリシーを構成して、Skype を追加の PIC プロバイダーとして表示する必要があります。

<div>


> [!NOTE]
> また、管理者が少なくとも 1 つのポリシー (この手続きの手順 2.) を構成してパブリック IM 接続をサポートするまでは、パブリック インスタント メッセージング接続 (PIC) サービス プロバイダーのユーザーは組織の IM や会議に参加できません。<BR>フェデレーションと PIC を構成するには、で<A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>「フェデレーションとパブリック IM 接続を有効または無効にする」を参照してください。<BR>フェデレーションさ<A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>れたユーザーアクセスをサポートするために、少なくとも1つのポリシーを構成するには、「パブリックユーザーアクセスを制御するためのポリシーの構成」を参照してください。



</div>

1.  Lync Server フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  次の 2 つのコマンドを実行します。
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > 環境に PIC プロバイダーがなく、新しい PIC プロバイダーを作成している場合は、 <STRONG>CsPublicProvider</STRONG>コマンドレットを実行する必要はありません。

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Lync Server 2013 CU5 以降&amp; lync デスクトップクライアントに OFFICE 2013 SP1 で追加されました。 lync ユーザーが Skype の連絡先を追加して、Microsoft 以外のドメインを「修飾」することができるようになりました。 NameDecorationRoutingDomain と NameDecorationExcludedDomainListSkype (: user (contoso) @msn の形式) を特定して、ルーティングします。 こうした新しい設定により、ユーザーが [Skype 連絡先の追加] ダイアログ ボックスに入力したアドレスに NameDecorationExcludedDomainList のドメイン (現在は msn.com、live.com、Hotmail.com、outlook.com に対応できます) が含まれない場合は、このアドレスの NameDecorationRoutingDomain による自動書式設定 (msn.com に設定する必要があります) が可能になります。

        
        </div>

3.  Lync クライアントから、PIC プロバイダとして Skype を選択できるようになりました。 Skype クライアントを追加するには、お客様の Microsoft アカウントを指定します。 さらに、Microsoft アカウントで統合してログインした Skype ユーザーは、連絡先要求を Lync ユーザーに送信できます。 Microsoft アカウントの詳細については、「 [microsoft アカウントとは](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)」を参照してください。 Lync にクライアントを追加する方法の詳細については、「lync を[使用したユーザーとしての Lync Server 2013 での lync の接続](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。

4.  ホストさ[https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)れているプロバイダーの変更の詳細については、の「ホステッド SIP フェデレーションプロバイダーを作成または編集する」を参照してください。

これで、サーバー上で実行する必要がある管理タスクが完了します。 これで Lync と Skype の接続が設定されました。

</div>

</div>

<div>

## <a name="additional-resources"></a>その他のリソース

[エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Lync Server 2013 での Lync と Skype の接続のプロビジョニング ガイド](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

