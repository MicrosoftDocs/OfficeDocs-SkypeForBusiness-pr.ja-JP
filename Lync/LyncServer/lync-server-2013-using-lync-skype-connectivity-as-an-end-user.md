---
title: 'Lync Server 2013: エンドユーザーとしての Lync-Skype 接続の使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94bb9a2d5fa584de5b6195de0ad2accf6899d0e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535774"
---
# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>エンドユーザーとしての Lync Server 2013 での Lync-Skype 接続の使用

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-27_

接続を Lync-Skype すると、Skype ユーザーと Lync ユーザーは、連絡先、exchange インスタントメッセージ、および音声通話とビデオ通話を追加することができます。 Skype ユーザーが Lync ユーザーを追加すると、skype ユーザーは Lync ユーザーのセッション開始プロトコル (SIP) uniform resource identifier (URI) を含む Skype の連絡先を作成します。 反対に、Lync ユーザーが Skype 連絡先を追加すると、lync ユーザーは skype ユーザー名ではなく、Skype ユーザーの Microsoft アカウント (MSA) を含む Lync で連絡先を作成します。

**MSA とは** Skype ユーザーは、Lync の連絡先と通信するために、Microsoft アカウント (旧称 Windows Live ID) を使用して Skype にサインインする必要があります。Microsoft アカウントは、電子メールアドレスとパスワードの組み合わせで構成されており、Microsoft OneDrive ストレージテクノロジ、Windows Phone、Microsoft Xbox LIVE ゲームサービス、Microsoft Outlook メッセージングおよびコラボレーションクライアント (および以前の Microsoft Hotmail web ベースの電子メールサービスまたは Windows Live Messenger) などのサービスへのサインインにも使用できます。電子メールアドレスとパスワードを使用して、これらのサービスまたはその他のサービスにサインインする場合は、既に Microsoft アカウントを持っています。Microsoft アカウントの作成の詳細については、Microsoft アカウントのサインアップページ () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) 。 既存の Skype アカウントを、さまざまなアプリケーションやサービスのシングルサインオン用の Microsoft アカウントに結合することができます。 アカウントが結合されると、Skype ユーザーは Lync ユーザーに対して連絡先要求を送信できるようになります。

<div>


> [!IMPORTANT]  
> Lync および Skype ユーザーがお互いに完全に通信できるようにするには、次の要件を満たす必要があります。 
> <UL>
> <LI>
> <P>Skype ユーザーは、Microsoft アカウント (MSA) を使用して Skype クライアントにログインしている必要があります。</P>
> <LI>
> <P>Lync ユーザーは、Lync 管理者がパブリック IM 接続を有効にしている必要があります。</P>
> <LI>
> <P>Skype ユーザーが Lync 連絡先を追加するときに、連絡先の名前の下に「Lync」という語句が表示されることを確認します。 これは、Lync URI が見つかったことを示します。</P>
> <LI>
> <P>Skype ユーザーが lync 連絡先を追加し、その Lync ドメインに対して検索結果がゼロで返された場合、PIC プロビジョニングプロセスが完了していないか、または Lync ドメインがまだセットアップされていない可能性があります。</P>
> <LI>
> <P>Lync および Skype ユーザーのプライバシー設定によっては、新しい連絡先が各ユーザーによって承認されるまで、IM、ビデオ、プレゼンスが機能しない場合があります。</P></LI></UL>



</div>

**Skype 連絡先を Lync 2013 に追加するには**

1.  Lync で、[ **連絡先の追加] をクリックし、自分の組織にない連絡先を追加**します。

2.  利用可能な連絡先プロバイダーのリストから、[ **Skype**] を選択します。

3.  [ **IM アドレス** ] フィールドに、Skype ユーザーの Microsoft アカウント (MSA) を入力します。

4.  [ **連絡先グループに追加** ] ドロップダウンボックスで、ユーザーを追加する連絡先グループを選択します。

5.  [ **プライバシー関係の設定** ] ドロップダウンボックスで、適切な連絡先設定を選択し、[ **OK]** をクリックします。

6.  これで、ユーザーは Lync に連絡先として表示されるようになります。 ユーザーを選択し、ユーザー名を右クリックし、[ **連絡先カードを表示** する] をクリックしてユーザーのプロパティを表示します。 新しく追加された Skype ユーザーとの音声またはビデオ通話を確立できるようになりました。

連絡先のサポートの詳細については、「 [Lync の連絡先を追加する](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)」を参照してください。

Skype ユーザーの Microsoft アカウントで <strong>bob@contoso.com</strong> などのカスタムドメイン名を使用すると、lync ユーザーは次の2つの方法で microsoft アカウントを lync に追加できます。

1.  [ **連絡先の追加** ] アイコンを使用するか、

2.  [ **人物または会議室を探す] または [電話番号をダイヤル** する] フィールドを使用します。

各インスタンスで、Lync ユーザーは Skype ユーザーの電子メールを次の形式で入力する必要があります。 <strong>ユーザー (ドメイン名) @msn .com</strong> 。

<div>


> [!IMPORTANT]  
> この手順は、次のドメイン名を使用する Microsoft アカウントには必要ありません。 <STRONG>@live .com、@hotmail、または @outlook</STRONG>。 サポートされているカスタムドメイン名の詳細については、「 <A href="https://support.microsoft.com/kb/897567">サポートされているパブリック IM ドメイン</A>」を参照してください。



</div>

**カスタムドメイン名を使用して Skype 連絡先を Lync に追加するには**

1.  Lync で、[ **連絡先の追加] をクリックし、自分の組織にない連絡先を追加**します。

2.  利用可能な連絡先プロバイダーのリストから、[ **Skype**] を選択します。

3.  [ **IM アドレス** ] フィールドに、ユーザーの形式 <strong>(ドメイン名) @msn</strong>で、Skype ユーザーの Microsoft アカウント (MSA) を入力します。 このため、ユーザー bob@contoso.com の場合、このエントリは <strong> bob (@msn) <strong> となります。

4.  [ **連絡先グループに追加** ] ドロップダウンリストボックスで、ユーザーを追加する連絡先グループを選択します。

5.  [ **プライバシー関係の設定** ] ドロップダウンリストボックスで、適切な連絡先設定を選択し、[ **OK]** をクリックします。

6.  Lync ユーザーは、[人の検索] または [会議室] を使用したり、Lync で **電話番号の** フィールドにダイヤルしたり、次のようなアドレスを追加したりすることもできます <strong>(ドメイン名) @msn .com</strong> 。 そのため、bob@contoso.com Microsoft アカウントの場合、このエントリは <strong>bob (@msn)</strong> となります。

7.  連絡先を連絡先グループに追加し、適切なプライバシー関係を選択するには、上記の手順4と5に従います。

**Lync 連絡先を Skype に追加するには**

1.  Skype にサインインします。 Skype ユーザーは、Microsoft アカウント (MSA) を使用して Skype クライアントにログインしている必要があります。

2.  [連絡先の追加] アイコンを選択します。

3.  Lync ユーザーの SIP URI を入力します。 たとえば、bob@contoso.com です。

4.  検索結果で一致するものが見つかった場合は、Lync ユーザー名の下にある word **lync** を検索します。 これは、Skype が Lync クライアントの SIP URI に正常に配置されたことを示します。 名前をクリックします。

5.  ウィンドウの右上にある [連絡先に追加] をクリックします。

6.  連絡先リストに新しい連絡先が追加されましたが、要求を承諾するまでは、[状態] アイコンではなく、疑問符が表示されます。 新しい連絡先が要求を受信すると、オンライン状態を確認したり、IM 会話を開始したり、音声およびビデオ通話を行ったりすることができます。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 管理者は、受信要求を許可するように Lync ユーザーのポリシー設定を構成する必要があります。 それ以外の場合、Lync ユーザーは Skype ユーザーからの連絡先要求を受信しません。 Lync ユーザーのポリシー設定の構成によっては、Skype ユーザーを追加する要求が Lync クライアントの [ <STRONG>新規作成</STRONG> ] タブに表示されます。Skype ユーザーとの通信を開始するには、Lync ユーザーが [お気に入り] 一覧または連絡先リストに Skype ユーザーを追加する必要があります。 下の図は、Lync クライアントの <STRONG>新しい</STRONG> タブの場所を示しています。

    
    </div>

Lync ユーザーは、Skype ユーザーから送信された要求が Lync ユーザーに表示され、検出可能であることを確認するために、Lync alerts を構成する必要があります。 Lync alerts を構成するには、次の手順を実行します。

**Lync Alerts を構成するには**

1.  Lync クライアントから、[ **オプション** ] アイコンをクリックします。

2.  [ **通知**] を選択します。

3.  [ **一般的な通知**] で、自分の **連絡先リストにユーザーが追加されたときに**[通知] をオンにします。

4.  [ **Lync を使用しない連絡先**] で、[ **招待を許可するが、他のすべての通信をブロックする**] を選択します。

5.  [ **OK]** をクリックして、[オプション] ウィンドウを閉じます。

</div>

<span> </span>

</div>

</div>

</div>

