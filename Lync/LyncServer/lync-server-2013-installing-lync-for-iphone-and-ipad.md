---
title: 'Lync Server 2013: Lync for iPhone および iPad をインストールする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for iPhone and iPad
ms:assetid: 88d1c149-5842-4ecf-a15e-fcda0330325b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690987(v=OCS.15)
ms:contentKeyID: 51541496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0383fd4aa389912a9942d7cafd7ac22fdc4f477
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-iphone-and-ipad-in-lync-server-2013"></a>Lync for iPhone および iPad を Lync Server 2013 にインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-03-10_

Lync 2013 for iPhone および Lync 2013 for iPad は、Apple App Store で利用できるユーザーがインストールできるアプリケーションです。

<div>

## <a name="installing-lync-for-iphone-and-lync-for-ipad"></a>Lync for iPhone および Lync for iPad をインストールする

ユーザーに対して Lync 2013 for iPhone と Lync 2013 for iPad をインストールするように指示するには、そのユーザーをデバイスから App Store に指示します。 各デバイスの App Store は、オンラインでも利用できます。

  - Lync for iPhone は、 \< h<span></span>ttp://www.apple.com/iphone/from-the-app-store/の App Store で参照できます >

  - Lync for iPad は、ht \< <span></span>tp://www.apple.com/ipad/from-the-app-store/で App Store で利用できます >

<div>


> [!IMPORTANT]  
> Lync 2013 アプリをインストールしておらず、会議出席依頼から Lync 会議に参加しようとしている iPhone ユーザーは、[参加] 起動ツールページにリダイレクトされます。 このページには、Lync 2013 アプリをインストールするためのリンクが含まれています。 ただし、アプリストアにユーザーを誘導する代わりに、このリンクを使うと、空白の Safari ブラウザーページが開きます。 この問題を回避するには、次の2つの操作を実行します。 
> <UL>
> <LI>
> <P>[<STRONG>ホーム</STRONG>] ボタンを使用して safari ページをバックグラウンドに送信し、次に safari をもう一度開きます。 [このページを App Store で開く] という通知が表示されたら、[<STRONG>開く</STRONG>] をタップして、app Store の Lync 2013 ダウンロードに移動します。</P>
> <LI>
> <P>App Store を手動で開いて、"Lync 2013" を検索し、アプリをダウンロードします。</P></LI></UL>



</div>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>モバイルクライアントのインストールを確認する

クライアントを構成して正常にサインインしたら、次のテストを行って、お使いのモバイルデバイスで Lync インストールが正常に動作していることを確認します。

**会社のディレクトリにある連絡先の検索**

1.  連絡先リストの最上部にある検索バーの内側をタップし、グローバル アドレス一覧 (GAL) のみに存在する連絡先の名前の入力を開始します。

2.  連絡先名が検索結果に表示されることを確認します。

**インスタント メッセージングおよびプレゼンスのテスト**

1.  連絡先リストで、連絡先をタップします。

2.  連絡先カードで、[ **IM** ] をタップします。

3.  インスタント メッセージング (IM) ウィンドウが表示され、IM の入力と送信が可能であることを確認します。

**ダイヤルアウト会議のテスト**

1.  Outlook で Lync 会議をスケジュールします。

2.  モバイル デバイスで、会議の招待状を開きます。

3.  参加する会議のリンクをクリックします。

4.  会議サービスからの呼び出しに応答し、会議の音声部分に接続されていることを確認します。

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

