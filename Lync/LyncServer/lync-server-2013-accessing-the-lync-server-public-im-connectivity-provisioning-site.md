---
title: 'Lync Server 2013: Lync Server パブリック IM 接続プロビジョニング サイトへのアクセス'
TOCTitle: Lync Server パブリック IM 接続プロビジョニング サイトへのアクセス
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn440174(v=OCS.15)
ms:contentKeyID: 59602754
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 から Lync Server パブリック IM 接続プロビジョニング サイトへのアクセス

 

_**トピックの最終更新日:** 2017-03-09_

以前の PIC プロビジョニングの方法と比較すると、Lync と Skype の接続のプロビジョニング プロセスには変更点があります。このプロビジョニング プロセスは、完了するまで最長で 30 日かかる可能性があります。Microsoft は、このドキュメントの残りの手順を完了する前に、このプロセスを先に開始することをお勧めします。アカウントに関する Lync と Skype の接続のプロビジョニング プロセスが完了した後、アカウントがアクティブになり、適格なユーザーのパブリック IM 接続が有効になります。

### Lync と Skype の接続をプロビジョニングするには、次の情報が必要です。

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
<tr class="even">
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


### Lync と Skype の接続のプロビジョニング プロセスを開始するには:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft Windows Live ID を使用して、Web サイト <strong>https://pic.lync.com</strong> にサインインします。</p></li>
<li><p>Microsoft ライセンスの契約の種類を選びます。</p></li>
<li><p>チェック ボックスをオンにし、Lync Server の製品使用権の内容を読んで同意したことを確認します。</p></li>
<li><p><strong>プロビジョニング要求を開始する</strong>ためのページで、適切なリンクをクリックして次のようなプロビジョニング要求を開始します。</p></li>
<li><p><strong>プロビジョニング情報を指定する</strong>ためのページで、<strong>アクセス エッジ サービスの FQDN</strong> を入力します。たとえば、<strong>accessedge.contoso.com</strong> と入力します。</p></li>
<li><p>少なくとも 1 つの SIP ドメイン名を入力し、[<strong>追加</strong>] をクリックします。</p>

> [!IMPORTANT]
> プロビジョニング プロセスを完了するには、少なくとも 1 つのアクセス エッジ サーバーと 1 つの SIP ドメインが必要です。SIP ドメインとアクセス エッジ サーバーは、アクティブで、正常に機能し、ネットワーク上で到達可能である必要があります。


</li>
<li><p>[<strong>パブリック IM サービス プロバイダー</strong>] の一覧で [<strong>Skype</strong>] を選び、[<strong>次へ</strong>] をクリックして連絡先情報を追加し、プロビジョニング要求を送信します。</p></li>
</ol></td>
</tr>
<tr class="even">
<td><ol>
<li><p>Microsoft Windows Live ID を使用して、Web サイト <strong>https://pic.lync.com</strong> にサインインします。</p></li>
<li><p>Microsoft ライセンスの契約の種類を選びます。</p></li>
<li><p>チェック ボックスをオンにし、Lync Server の製品使用権の内容を読んで同意したことを確認します。</p></li>
<li><p><strong>プロビジョニング要求を開始する</strong>ためのページで、適切なリンクをクリックして次のようなプロビジョニング要求を開始します。</p></li>
<li><p><strong>プロビジョニング情報を指定する</strong>ためのページで、<strong>アクセス エッジ サービスの FQDN</strong> を入力します。たとえば、<strong>accessedge.contoso.com</strong> と入力します。</p></li>
<li><p>少なくとも 1 つの SIP ドメイン名を入力し、[<strong>追加</strong>] をクリックします。</p>

> [!IMPORTANT]
> プロビジョニング プロセスを完了するには、少なくとも 1 つのアクセス エッジ サーバーと 1 つの SIP ドメインが必要です。SIP ドメインとアクセス エッジ サーバーは、アクティブで、正常に機能し、ネットワーク上で到達可能である必要があります。


</li>
<li><p>[<strong>パブリック IM サービス プロバイダー</strong>] の一覧で [<strong>Skype</strong>] を選び、[<strong>次へ</strong>] をクリックして連絡先情報を追加し、プロビジョニング要求を送信します。</p></li>
</ol></td>
</tr>
</tbody>
</table>


プロビジョニング要求が送信された後、アカウントをアクティブにして、ユーザーをパブリック IM 接続で有効にするには、最長で 30 日かかる可能性があります。

## フェデレーションとパブリック IM 接続 (PIC) の有効化

プロビジョニング要求を送信した後は、Lync と Skype の接続を構成するために必要な、Lync Server の環境と管理タスクに重点を移すことができます。このセクションでは、Lync Server 管理者は Lync Server を展開し、外部アクセスを構成していることが前提になっています。Lync Server 向けの外部アクセスの構成について詳細については、「外部ユーザー アクセスの計画」( [http://go.microsoft.com/fwlink/p/?LinkID=273772](http://go.microsoft.com/fwlink/p/?linkid=273772)) および「外部ユーザー アクセスの展開」( [http://go.microsoft.com/fwlink/p/?LinkID=27378](http://go.microsoft.com/fwlink/p/?linkid=27378)) を参照してください。

Lync と Skype の接続向けに Lync Server 環境を準備するには、Lync Server 管理者は次の 3 つのタスクを完了する必要があります。

## 1\. フェデレーションと PIC を構成する

フェデレーションは、Skype ユーザーが組織内の Lync ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Lync ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、次に示すように Lync Server コントロール パネルを使用して構成します。


> [!IMPORTANT]
> PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。PIC フェデレーションがサポートされるプラットフォームとしては、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。



## 2\. フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する

管理者は Lync Server コントロール パネルを使用して外部ユーザー アクセス ポリシーを 1 つ以上構成し、Skype ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御する必要があります。

## 3\. Lync 用の Skype PIC プロバイダー設定を構成する

管理者は Lync Server 管理シェルを使用して Lync クライアント ポリシーを構成し、Skype を追加の PIC プロバイダーとして表示する必要があります。

> [!Note]  
> また、管理者が少なくとも 1 つのポリシー (この手続きの手順 2.) を構成してパブリック IM 接続をサポートするまでは、パブリック インスタント メッセージング接続 (PIC) サービス プロバイダーのユーザーは組織の IM や会議に参加できません。<br />
> フェデレーションと PIC を構成するには、「フェデレーションおよびパブリック IM 接続の有効化または無効化」( <a href="http://go.microsoft.com/fwlink/p/?linkid=306063">http://go.microsoft.com/fwlink/p/?LinkId=306063</a>) を参照してください。<br />
> 少なくとも 1 つのポリシーを構成してフェデレーション ユーザーのアクセスをサポートするには、「パブリック ユーザー アクセスを制御するポリシーの構成」( <a href="http://go.microsoft.com/fwlink/p/?linkid=306064">http://go.microsoft.com/fwlink/p/?LinkId=306064</a>) を参照してください。


1.  Lync Server フロント エンド サーバーから、Lync Server 管理シェルを開きます。

2.  次の 2 つのコマンドを実行します。
    
      - Remove-CsPublicProvider -Identity Messenger
    
      - New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger\_16x16.png" -VerificationLevel 2 -Enabled 1

3.  この時点で、Lync クライアントから Skype を PIC プロバイダーとして選び、また Microsoft アカウントを指定して Skype クライアントを追加することができます。加えて、マージされ Microsoft アカウントでログインした Skype ユーザーは、連絡先追加のリクエストを Lync ユーザーに送ることができます。Microsoft アカウントの詳細については、「[Microsoft アカウントとは何ですか?](https://support.skype.com/ja/faq/fa12059/what-is-a-microsoft-account)」を参照してください。Lync へのクライアントの追加の詳細については、「[エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)」を参照してください。

4.  ホストされるプロバイダーの変更の詳細については、「ホスト SIP フェデレーション プロバイダーの作成または編集」( [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)) を参照してください。

これで、サーバー上で実行する必要がある管理タスクが完了し、Lync と Skype の接続を使用するように設定されました。

## その他のリソース

[エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Provisioning guide for Lync-Skype connectivity in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

