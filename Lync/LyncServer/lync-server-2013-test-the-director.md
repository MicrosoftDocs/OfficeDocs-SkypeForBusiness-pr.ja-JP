---
title: 'Lync Server 2013: ディレクターのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae7f2945cd3a21ea93969e098110fadec710cb98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519094"
---
# <a name="test-the-director-in-lync-server-2013"></a>Lync Server 2013 でのディレクターのテスト

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

この段階ではディレクターまたはディレクタープールが構成されていますが、ドメインネームシステム (DNS) SRV エントリは、プールまたは Standard Edition サーバーを使用してログオンするためにクライアントをポイントします。 Lync 2013 クライアントがディレクターを使用して自動的にログオンするように DNS レコードを変更する前に、手動でディレクターをポイントしてクライアントをテストします。

<div>

## <a name="to-test-the-deployment"></a>展開をテストするには

1.  **Csadministrator**グループの一部であるドメインアカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  ナビゲーションウィンドウで、[ **トポロジ**] をクリックし、[ **状態** ] 列に、ディレクターまたはディレクタープール用の矢印 ( ![緑色の矢印](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "緑の矢印付きのサーバーアイコン")が表示されているサーバーアイコン) が付いた緑色のサーバーがあることを確認します。

4.  Lync Server 2013 クライアントがインストールされている2台のクライアントコンピューターを接続し、Lync Server 2013 で有効になっている別のユーザーアカウントを使用して各コンピューターにログオンします。

5.  いずれかのクライアントコンピューターで [ **オプション** ] メニューをクリックし、[ **個人用** 設定] グループを選択して、[ **詳細**設定]、[ **手動構成**] の順にクリックし、[ **内部サーバー名または IP アドレス** ] に新しいディレクターまたはディレクタープールの完全修飾ドメイン名 (FQDN) を設定します。

6.  両方のクライアントにログオンし、ディレクターを使用してログオンしたクライアントが正常にログオンできること、またはその他のユーザーのプレゼンス状態を表示して、インスタントメッセージを交換できることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

