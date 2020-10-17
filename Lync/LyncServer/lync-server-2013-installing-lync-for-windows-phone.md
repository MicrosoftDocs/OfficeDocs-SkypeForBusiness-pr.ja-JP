---
title: 'Lync Server 2013: Lync for Windows Phone のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ac77a8402a62929bcb043ebd165a41605b17351
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514184"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Lync Server 2013 での Lync for Windows Phone のインストール

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-03_

Windows phone 用 Lync 2013 は、ユーザーがインストールできるアプリケーションで、Windows Phone Marketplace で利用できます。

<div>

## <a name="installing-lync-for-windows-mobile"></a>Lync for Windows Mobile のインストール

ユーザーに対して、Lync 2013 for Windows Phone をデバイスにインストールするように指示するには、を使用 <https://go.microsoft.com/fwlink/p/?linkid=231901> します。

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>DNS SRV レコードを使用して Exchange Web サービスを公開する場合

Lync クライアントに対して Exchange 統合を有効にするために、一部の組織では、DNS SRV レコードを使用して Exchange Web サービスの URL を公開しています。 「Microsoft ダウンロードセンター」に記載されている「Exchange 統合について理解し、トラブルシューティングを行う」では [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) 、これが必要になるシナリオについて説明しています。 ただし、windows phone プラットフォームでは SRV 参照がサポートされていないため、Windows Phone ユーザーの Exchange 統合はこのシナリオでは機能しません。 電話でサーバーを自動的に検出するのではなく、Windows Phone のユーザーに Exchange Web サービスの URL を指定するように指示する必要があります。

ユーザーに、Windows Phone で Lync の設定を次のように構成するように指示します。

1.  Windows Phone の [Lync の設定] で、[ **Exchange** ] 画面を選択します。

2.  **自動検出サーバー**を**オフ**に移動します。

3.  空のフィールドをタップして、Exchange Web サービスの完全修飾ドメイン名 (FQDN) または URL を入力します。
    
    <div>
    

    > [!NOTE]  
    > 完全修飾ドメイン名 (FQDN) または Exchange Web サービスサーバーの完全な URL のいずれかを指定できます。 FQDN を指定すると、プロトコル (https://) と Exchange Web サービスパス (/ews/exchange.asmx) が自動的に追加されます。 Exchange Web サービスのパスが異なる場合は、完全な URL を指定できます。

    
    </div>

4.  画面を閉じます。

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>モバイル クライアント インストールの検証

クライアントを構成して正常にサインインしたら、次のテストを使用して、Lync 2013 のインストールがモバイルデバイスで正しく動作することを確認します。

**会社のディレクトリにある連絡先の検索**

1.  連絡先一覧で、下部にある [ **検索** ] をタップします。

2.  グローバルアドレス一覧にのみ存在する連絡先を検索します。

3.  連絡先名が検索結果に表示されることを確認します。

**インスタントメッセージングとプレゼンスのテスト**

1.  連絡先一覧で、連絡先をタップします。

2.  連絡先カードで、[**IM**] アイコンをタップします。

3.  インスタントメッセージング (IM) ウィンドウが表示され、IM の入力と送信が可能であることを確認します。

**ダイヤルアウト会議のテスト**

1.  Outlook で、Lync 会議をスケジューリングします。

2.  モバイル デバイスで、会議の招待状を開きます。

3.  参加する会議のリンクをクリックします。

4.  電話会議サービスからの呼び出しに応答し、会議のオーディオに接続していることを確認します。

**プッシュ通知のテスト**

1.  ユーザー A のモバイル デバイスで、ユーザー A のアカウントを使用して Lync にサインインします。

2.  モバイル デバイスで別のアプリケーションを開きます。

3.  異なるクライアントで、ユーザー B のアカウントを使用して Lync にサインインします。

4.  IM をユーザー B からユーザー A に送信します。

5.  IM 通知がユーザー A のモバイル デバイスに表示されていることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

