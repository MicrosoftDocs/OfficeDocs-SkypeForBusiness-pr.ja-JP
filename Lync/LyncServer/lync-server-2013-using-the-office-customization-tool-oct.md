---
title: 'Lync Server 2013: Office カスタマイズツール (OCT) の使用'
description: 'Lync Server 2013: Office カスタマイズツール (OCT) の使用。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 602502ba4579ed6c640eee909d4c6b056ce247d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547333"
---
# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Lync Server 2013 で Office カスタマイズツール (OCT) を使用する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Office カスタマイズツール (OCT) はセットアッププログラムの一部であり、多くのカスタマイズに推奨されるツールです。 OCT を使用して、Office をカスタマイズし、カスタマイズをセットアップカスタマイズ .msp ファイルに保存します。 このファイルは、ネットワークインストールポイントの Updates フォルダーに配置します。 Office をインストールすると、セットアッププログラムによって Updates フォルダーのセットアップカスタマイズファイルが検索され、カスタマイズが適用されます。 Updates フォルダーは、Office 2013 の初期インストール時にソフトウェア更新プログラムを展開する場合にのみ使用できます。

OCT はセットアップの一部であり、ボリュームライセンスバージョンの製品に含まれています。 OCT を実行するには、 `setup.exe /admin` Office 2013 ソースファイルが含まれているネットワークインストールポイントのルートからコマンドラインを入力します。 たとえば、次の値を使用します。

`\\server\share\Office15\setup.exe /admin`

管理者は OCT を使用して、セットアップカスタマイズ .msp ファイルを作成します。 Microsoft Office 2010 OCT と同様に、管理者は次の領域をカスタマイズできます。

  - **セットアップ** クライアントと既定の組織名の既定のインストール場所、追加のネットワークインストールソース、プロダクトキー、使用許諾契約書、表示レベル、削除する Office の以前のバージョン、インストール時に実行するカスタムプログラム、セキュリティ設定、およびセットアップのプロパティを指定するために使用します。

  - **機能** ユーザー設定を構成し、Office 機能のインストール方法をカスタマイズするために使用されます。 管理者は、OCT を使用して、ユーザーの Office アプリケーション設定の初期既定値を指定できます。 ユーザーはインストール後に大部分の設定を変更できます。

  - **その他のコンテンツ** ファイルを追加または削除したり、レジストリエントリを追加または削除したり、ショートカットを構成したりするために使用します。

  - **Outlook** ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange の設定の指定、アカウントの追加、アカウントの削除と設定のエクスポート、および送信受信グループの指定に使用され \\ ます。

OCT の詳細については、「」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=267516> 。

</div>

<span> </span>

</div>

</div>

</div>

