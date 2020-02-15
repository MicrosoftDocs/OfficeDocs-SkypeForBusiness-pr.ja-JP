---
title: 'Lync Server 2013: 会議出席依頼の構成'
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
ms.openlocfilehash: 5697605b4560fc91a153869204756f0ddda356fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Lync Server 2013 での会議出席依頼の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-16_

Lync 2013 用のオンライン会議アドインによって送信される会議出席依頼をカスタマイズするには、会議出席依頼の本文に次のオプションの項目を含めます。

  - **組織のロゴ**[ロゴの URL] オプションを使用して、組織のロゴを会議出席依頼に追加します。 組織外のユーザーに会議出席依頼を送信する場合、画像は公開されている URL に配置する必要があります。 サポートされている画像形式は、GIF および JPG です。 Lync Server 2013 はイメージにサイズ制限のない URL を格納していますが、最適な結果を得るには、画像の最大サイズを30ピクセル、高さを188ピクセルにする必要があります。

  - **カスタムヘルプまたはサポートリンク**組織のヘルプまたはサポートチーム web サイトの URL を追加します。 組織外のユーザーに会議出席依頼が送信される場合は、URL が公開されている必要があります。 URL の最大の長さは 1 KB です。

  - **法的免責事項のテキスト**すべての会議出席依頼に表示されるリーガルテキストまたは免責事項の URL を追加します。 組織外のユーザーに会議出席依頼が送信される場合は、URL が公開されている必要があります。 URL の最大の長さは 1 KB です。

  - **カスタムフッターテキスト**招待状にカスタムフッターとして表示されるテキストを追加します。 追加できるテキストの最大文字数は 2 KB です。

これらのオプションは、Lync Server コントロールパネルまたは Lync Server 管理シェルのいずれかを使用して構成できます。

<div>


**Lync Server コントロールパネルを使用して会議出席依頼をカスタマイズするには**

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。

4.  [**会議の構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。
    
      - サイト レベルのポリシーを作成するには、[**サイト構成**] をクリックします。[**サイトの選択**] 検索フィールドに、会議参加設定を定義するサイトの名前の全体または一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。
    
      - プール レベルのポリシーを作成するには、[**プール構成**] をクリックします。[**サービスの選択**] 検索フィールドに、会議参加設定を定義するプール サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のプールをクリックして [**OK**] をクリックします。

5.  次のどちらかの操作を行います。
    
      - [**ロゴの url** ] フィールドに、組織のロゴ画像の url を入力します。
    
      - [**ヘルプ url** ] フィールドに、組織のヘルプまたはサポートサイトへの url を入力します。
    
      - [**リーガル] テキスト**フィールドに、会議出席依頼に含める法的なテキストまたは免責事項の URL を入力します。
    
      - [**ユーザー設定のフッターテキスト**] フィールドに、フッターテキストを入力します (最大 2 KB)。

**Lync Server 管理シェルを使用して会議出席依頼をカスタマイズするには**

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  **新しい-csmeeting 構成**または**Set-csmeeting 構成**コマンドレットを実行して、会議への招待のオプションを作成または構成します。 たとえば、以下を実行します。
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

