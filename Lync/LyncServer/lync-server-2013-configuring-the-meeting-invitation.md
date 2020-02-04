---
title: 'Lync Server 2013: 会議の出席依頼を設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14e0614ecdaa73a886429e89618cac568d620938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Lync Server 2013 で会議出席依頼を設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-16_

Lync 2013 用のオンライン会議アドインで送信された会議出席依頼をカスタマイズするには、会議出席依頼の本文に次のオプションの項目を含めます。

  - **組織のロゴ**[ロゴの URL] オプションを使用して、組織のロゴを会議出席依頼に追加します。 会議の出席依頼が組織外のユーザーに送信される場合、画像は公開されている URL である必要があります。 サポートされている画像形式は、GIF と JPG です。 Lync Server 2013 には、画像のサイズ制限のない URL が保存されていますが、最適な結果を得るには、画像の最大サイズは、高さ30ピクセル、幅188ピクセルです。

  - **カスタムヘルプまたはサポートリンク**組織のヘルプまたはサポートチームの web サイトの URL を追加します。 会議の出席依頼が組織外のユーザーに送信される場合、URL は公開されている必要があります。 URL の最大長は 1 KB です。

  - **法的免責事項のテキスト**すべての会議出席依頼に表示される法的テキストまたは免責事項の URL を追加します。 会議の出席依頼が組織外のユーザーに送信される場合、URL は公開されている必要があります。 URL の最大長は 1 KB です。

  - **ユーザー設定のフッターテキスト**招待状にカスタムフッターとして表示されるテキストを追加します。 追加できるテキストの最大文字数は 2 KB です。

Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、これらのオプションを構成できます。

<div>


**Lync Server コントロールパネルを使用して会議出席依頼をカスタマイズするには**

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。

4.  [**会議の構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。
    
      - サイト レベルのポリシーを作成するには、[**サイト構成**] をクリックします。[**サイトの選択**] 検索フィールドに、会議参加設定を定義するサイトの名前の全体または一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。
    
      - プール レベルのポリシーを作成するには、[**プール構成**] をクリックします。[**サービスの選択**] 検索フィールドに、会議参加設定を定義するプール サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のプールをクリックして [**OK**] をクリックします。

5.  次のいずれかの操作を実行します。
    
      - [**ロゴの url** ] フィールドに、組織のロゴ画像の URL を入力します。
    
      - [**ヘルプ URL** ] フィールドに、組織のヘルプまたはサポートサイトの url を入力します。
    
      - [**法的テキスト**] フィールドに、会議出席依頼に含める法的なテキストまたは免責事項の URL を入力します。
    
      - [**ユーザー設定のフッターテキスト**] フィールドに、「フッターテキスト」と入力します (最大 2 KB)。

**Lync Server 管理シェルを使用して会議出席依頼をカスタマイズするには**

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  **新しい csmeeting 構成**を実行するか、または**セットアップ**して、会議出席依頼のオプションを作成または構成します。 たとえば、以下を実行します。
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

