---
title: 'Lync Server 2013: ディレクターのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Lync Server 2013 でのディレクターのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

この段階では、ディレクターまたはディレクタープールが構成されていますが、ドメインネームシステム (DNS) SRV エントリは、プールまたは Standard Edition サーバーを使用して、クライアントのログオンをポイントします。 Lync 2013 クライアントがディレクターを使用して自動的にログオンするように DNS レコードを変更する前に、手動でディレクターをポイントしてクライアントをテストします。

<div>

## <a name="to-test-the-deployment"></a>展開をテストするには

1.  **Csadministrator**グループの一部であるドメインアカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  ナビゲーションウィンドウで、[**トポロジ**] をクリックし、[**状態**] 列で、ディレクターまたはディレクタープールの矢印が付いた![](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "")緑のサーバーがあることを確認します (つまり、緑色の矢印が表示されたサーバーアイコンが緑の矢印で表示されています)。

4.  Lync Server 2013 クライアントがインストールされている2つのクライアントコンピューターを接続して、Lync Server 2013 用に有効になっている別のユーザーアカウントを使用して、各コンピューターにログオンします。

5.  いずれかのクライアントコンピューターで、[**オプション**] メニューをクリックし、[**個人**設定] グループを選択し、[**詳細**設定] をクリックし、[**手動構成**] をクリックして、**内部サーバー名または IP アドレス**を [完全修飾] に設定します。新しいディレクターまたはディレクタープールのドメイン名 (FQDN)。

6.  両方のクライアントにログオンして、ディレクターを使用してログオンするクライアントが正常にログオンできることを確認し、他のユーザーのプレゼンス状態を確認して、インスタントメッセージを交換できることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

