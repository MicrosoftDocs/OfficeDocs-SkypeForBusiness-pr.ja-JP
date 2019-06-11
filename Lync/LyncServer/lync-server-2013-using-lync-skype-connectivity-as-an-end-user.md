---
title: 'Lync Server 2013: エンド ユーザーとしての Lync と Skype の接続の使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2bf4584f3332171942f941cc382d22bb6a8db7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-27_

Lync-skype 接続を使うと、Skype ユーザと Lync ユーザがお互いをコンタクトとして追加したり、インスタントメッセージを交換したり、音声通話やビデオ通話を発信したりできます。 Skype ユーザーが Lync ユーザーを追加すると、skype ユーザーは、Lync ユーザーのセッション開始プロトコル (SIP) uniform resource identifier (URI) を含む連絡先を Skype で作成します。 一方、Lync ユーザーが Skype 連絡先を追加すると、lync ユーザーは、skype ユーザー名ではなく、Skype ユーザーの Microsoft アカウント (MSA) を含む Lync の連絡先を作成します。

**MSA とは何ですか?** Lync の連絡先と通信するためには、skype ユーザーが Microsoft アカウント (旧称 Windows Live ID) を使って Skype にサインインしている必要があります。Microsoft アカウントは、メールアドレスとパスワードの組み合わせで構成されます。また、Microsoft OneDrive ストレージテクノロジ、Windows Phone、Microsoft Xbox LIVE online ゲームサービス、Microsoft Outlook メッセージングなどのサービスへのサインインにも使用できます。共同作業クライアント (および以前は Microsoft Hotmail web ベースのメールサービスまたは Windows Live Messenger)。メールアドレスとパスワードを使って、これらのサービスまたは他のサービスにサインインする場合は、既に Microsoft アカウントを持っています。Microsoft アカウントの作成の詳細については、Microsoft アカウントのサインアップページを[https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)参照してください。 既存の Skype アカウントを、さまざまなアプリケーションやサービスで、シングルサインオン用の Microsoft アカウントに統合することができます。 アカウントを統合すると、Skype ユーザーは連絡先要求を Lync ユーザーに送信できます。

<div>


> [!IMPORTANT]  
> Lync と Skype ユーザーが相互に完全に通信するためには、次の要件を満たしている必要があります。 
> <UL>
> <LI>
> <P>Skype ユーザは、Microsoft アカウント (MSA) を使って Skype クライアントにログインしている必要があります。</P>
> <LI>
> <P>Lync ユーザーは、Lync 管理者によるパブリック IM 接続を有効にしている必要があります。</P>
> <LI>
> <P>Skype ユーザーが Lync の連絡先を追加するときに、連絡先の名前の下に "Lync" と表示されていることを確認します。 これは、Lync URI が検出されたことを示します。</P>
> <LI>
> <P>Skype ユーザーが Lync の連絡先を追加したときに、その Lync ドメインで検索結果がゼロで返されると、PIC プロビジョニングプロセスが完了していないか、Lync ドメインがまだセットアップされていない可能性があります。</P>
> <LI>
> <P>Lync および Skype ユーザーのプライバシー設定によっては、新しい連絡先が各ユーザーによって承認されるまで、IM、ビデオ、プレゼンスが機能しないことがあります。</P></LI></UL>



</div>

**Lync 2013 に Skype の連絡先を追加するには**

1.  Lync で、[**連絡先の追加] をクリックし、[組織外の連絡先を追加**] をクリックします。

2.  利用可能なコンタクトプロバイダのリストから「 **Skype**」を選択します。

3.  [ **IM アドレス**] フィールドに、Skype ユーザーの Microsoft アカウント (MSA) を入力します。

4.  [**連絡先グループに追加**] ドロップダウンボックスで、ユーザーを追加する連絡先グループを選びます。

5.  [**プライバシー関係の設定**] ドロップダウンボックスで、適切な連絡先の設定を選び、[ **OK]** をクリックします。

6.  これで、ユーザーが Lync に連絡先として表示されるようになります。 ユーザーを選び、ユーザー名を右クリックして、[**連絡先カードの表示**] をクリックし、ユーザーのプロパティを表示します。 新しく追加された Skype ユーザとの音声通話またはビデオ通話を確立できるようになりました。

連絡先のサポートの詳細については、「 [Lync で連絡先を追加する](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)」を参照してください。

Skype ユーザーの Microsoft アカウントでカスタムドメイン名 ( <strong>bob@contoso.com</strong>など) を使用している場合、lync ユーザーは、次の2つの方法で microsoft アカウントを lync に追加することができます。

1.  [**連絡先の追加**] アイコンを使用するか、

2.  [**ユーザーまたは会議室を検索] または [電話番号をダイヤル**する] フィールドを使用します。

各インスタンスでは、Lync ユーザーは、Skype ユーザーのメールを次の形式で入力する必要があります。<strong>ユーザー (ドメイン名) @msn .com</strong> 。

<div>


> [!IMPORTANT]  
> この手順は、次のドメイン名を使用する Microsoft アカウントには必要ありません。 <STRONG>@live .com、@hotmail .com、または @outlook</STRONG>。 サポートされているカスタムドメイン名の詳細については、「<A href="https://support.microsoft.com/kb/897567">サポートされているパブリック IM ドメイン</A>」を参照してください。



</div>

**カスタムドメイン名を使用しているときに、Lync に Skype 連絡先を追加するには**

1.  Lync で、[**連絡先の追加] をクリックし、[組織外の連絡先を追加**] をクリックします。

2.  利用可能なコンタクトプロバイダのリストから「 **Skype**」を選択します。

3.  [ **IM アドレス**] フィールドに、ユーザーの形式 (<strong>ドメイン名) @msn .com</strong>の Skype ユーザーの Microsoft アカウント (MSA) を入力します。 ユーザー bob@contoso.com の場合、エントリは<strong>bob (contoso) @msn になり<strong>ます。

4.  [**連絡先グループに追加**] ドロップダウンリストボックスで、ユーザーを追加する連絡先グループを選びます。

5.  [**プライバシー関係の設定**] ドロップダウンリストボックスで、適切な連絡先の設定を選び、[ **OK]** をクリックします。

6.  Lync ユーザーは、[ユーザーの**検索] または [会議室**] を使用したり、lync の電話番号をダイヤルしたり、次のようなアドレス<strong>(ドメイン名) @msn</strong>を追加したりすることもできます。 Bob@contoso.com Microsoft アカウントの場合、エントリは<strong>bob (contoso) @msn</strong>になります。

7.  連絡先グループに連絡先を追加して、適切なプライバシー関係を選択するには、上記の手順4と5を実行します。

**Lync の連絡先を Skype に追加するには**

1.  Skype にサインインします。 Skype ユーザは、Microsoft アカウント (MSA) を使って Skype クライアントにログインしている必要があります。

2.  [連絡先の追加] アイコンを選択します。

3.  Lync ユーザーの SIP URI を入力します。 たとえば、bob@contoso.com のようになります。

4.  検索結果で一致するものが見つかった場合は、Lync ユーザー名の下にある word **Lync**を探します。 これは、Skype が Lync クライアントの SIP URI を正常に見つけたことを示します。 名前をクリックします。

5.  ウィンドウの右上隅の [連絡先フォルダーに追加] をクリックします。

6.  これで、新しい連絡先が連絡先リストに追加されますが、ユーザーが要求を承認するまでは、[状態] アイコンの代わりに疑問符が表示されます。 新しい連絡先が要求を受け入れると、相手がオンラインであることを確認したり、IM で会話を開始したり、音声通話やビデオ通話を行ったりすることができます。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 管理者は、受信要求を許可するように Lync ユーザーのポリシー設定を構成する必要があります。 サポートされていない場合、Lync ユーザーは Skype ユーザーからのコンタクト要求を受信しません。 Lync ユーザーのポリシー設定の構成に応じて、Lync クライアントの [<STRONG>新規</STRONG>] タブに Skype ユーザーの追加要求が表示されます。Skype ユーザーとの通信を開始するには、Lync ユーザーが [お気に入り] の一覧または連絡先リストに Skype ユーザーを追加する必要があります。 次の図は、Lync クライアントでの<STRONG>新しい</STRONG>タブの場所を示しています。

    
    </div>

Lync ユーザーは、Skype ユーザーから送信された要求が表示され、Lync ユーザーが見つけられるようにするために、Lync 通知を設定する必要があります。 Lync の通知を構成するには、次の手順を実行します。

**Lync 通知を構成するには**

1.  Lync クライアントで、[**オプション**] アイコンをクリックします。

2.  [**通知**] を選びます。

3.  [**一般通知**] で、[**だれかの連絡先リストに追加された場合**に通知する] チェックボックスをオンにします。

4.  [ **Lync を使っていない連絡先**] で [**招待を許可するが、その他のすべての通信をブロックする**] を選択します。

5.  [ **OK** ] をクリックして [オプション] ウィンドウを閉じます。

</div>

<span> </span>

</div>

</div>

</div>

