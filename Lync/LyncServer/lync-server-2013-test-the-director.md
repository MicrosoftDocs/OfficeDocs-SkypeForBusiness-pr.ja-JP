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
ms.openlocfilehash: b82b8b7e494a66cf38fd27e37f322c79e95f801c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746077"
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

3.  ナビゲーションウィンドウで、[**トポロジ**] をクリックし、[**状態**] 列で、ディレクターまたはディレクタープールの矢印が付いた緑のサーバー (つまり、緑色の矢印が![付いたサーバーアイコン](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "緑色の矢印が付いたサーバーアイコン")) があることを確認します。

4.  Lync Server 2013 クライアントがインストールされている2つのクライアントコンピューターを接続して、Lync Server 2013 用に有効になっている別のユーザーアカウントを使用して、各コンピューターにログオンします。

5.  いずれかのクライアントコンピューターで、[**オプション**] メニューをクリックし、[**個人**設定] グループを選択し、[**詳細**設定] をクリックし、[**手動構成**] をクリックして、**内部サーバー名または IP アドレス**を新しいディレクターまたはディレクタープールの完全修飾ドメイン名 (FQDN) に設定します。

6.  両方のクライアントにログオンして、ディレクターを使用してログオンするクライアントが正常にログオンできることを確認し、他のユーザーのプレゼンス状態を確認して、インスタントメッセージを交換できることを確認します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

