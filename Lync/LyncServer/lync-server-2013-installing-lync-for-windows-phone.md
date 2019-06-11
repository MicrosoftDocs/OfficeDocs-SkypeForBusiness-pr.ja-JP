---
title: 'Lync Server 2013: Lync for Windows Phone をインストールする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeb8f43ea4f4db15a9a057bd0d7b24c55d858cb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Lync Server 2013 での Lync for Windows Phone のインストール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-03_

Windows Phone 用の Lync 2013 は、Windows Phone Marketplace で利用できる、ユーザーがインストールできるアプリケーションです。

<div>

## <a name="installing-lync-for-windows-mobile"></a>Lync for Windows Mobile をインストールする

ユーザーに windows phone 用の Lync 2013 をインストールするように指示するには、Windows Phone Marketplace を使用<http://go.microsoft.com/fwlink/p/?linkid=231901>します。

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>DNS SRV レコードを使用して Exchange Web サービスを公開している場合

Lync クライアントで Exchange の統合を有効にするには、一部の組織では DNS SRV レコードを使用して Exchange Web サービスの URL を公開します。 Microsoft ダウンロードセンターで利用可能な、「Exchange の統合について理解し[http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)、トラブルシューティングする」のドキュメントでは、これが必要になる可能性のあるシナリオについて説明します。 ただし、windows phone プラットフォームでは、SRV 参照がサポートされていないため、Windows Phone ユーザー向けの Exchange との統合は動作しません。 電話で自動的にサーバーを検出する代わりに、Windows Phone ユーザーに Exchange Web サービスの URL を指定するように指示する必要があります。

次のようにして、Windows Phone で Lync の設定を構成するようにユーザーに指示します。

1.  Windows Phone の Lync の [設定] で、[ **Exchange** ] 画面を選択します。

2.  **自動検出サーバー**を**オフ**にします。

3.  空のフィールドをタップして、Exchange Web Services の完全修飾ドメイン名 (FQDN) または URL を入力します。
    
    <div>
    

    > [!NOTE]  
    > 完全修飾ドメイン名 (FQDN) または Exchange Web サービスサーバーの完全な URL のいずれかを指定できます。 FQDN を指定すると、プロトコル (https://) と Exchange Web サービスのパス (/ews/exchange.asmx) が自動的に追加されます。 Exchange Web Services のパスが異なる場合は、完全な URL を指定できます。

    
    </div>

4.  画面を閉じます。

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>モバイルクライアントのインストールを確認する

クライアントを構成して正常にサインインしたら、次のテストを行って、お使いのモバイルデバイスで Lync 2013 が正常に動作していることを確認します。

**会社のディレクトリにある連絡先の検索**

1.  連絡先リストで、下部にある [**検索**] をタップします。

2.  グローバル アドレス一覧にだけ含まれる連絡先を検索します。

3.  連絡先名が検索結果に表示されることを確認します。

**インスタント メッセージングおよびプレゼンスのテスト**

1.  連絡先リストで、連絡先をタップします。

2.  連絡先カードで、[ **IM** ] をタップします。

3.  インスタント メッセージング (IM) ウィンドウが表示され、IM の入力と送信が可能であることを確認します。

**ダイヤルアウト会議のテスト**

1.  Outlook で Lync 会議をスケジュールします。

2.  モバイル デバイスで、会議の招待状を開きます。

3.  参加する会議のリンクをクリックします。

4.  会議サービスからの通話に応答し、会議のオーディオに接続していることを確認します。

**プッシュ通知のテスト**

1.  ユーザー A のモバイルデバイスで、ユーザー A のアカウントで Lync にサインインします。

2.  モバイル デバイスで別のアプリケーションを開きます。

3.  別のクライアントでは、ユーザー B のアカウントで Lync にサインインします。

4.  IM をユーザー B からユーザー A に送信します。

5.  IM 通知がユーザー A のモバイル デバイスに表示されていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

