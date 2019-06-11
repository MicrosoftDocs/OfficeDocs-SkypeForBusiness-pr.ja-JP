---
title: 'Lync Server 2013: Office カスタマイズツール (OCT) を使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd9c101b9098f9a5a6ac6088740c067039921b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Lync Server 2013 で Office カスタマイズツール (OCT) を使用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

Office カスタマイズ ツール (OCT) はセットアップ プログラムの一部であり、多くのカスタマイズにおける推奨ツールになっています。 OCT を使用して Office をカスタマイズし、カスタマイズ内容をセットアップ カスタマイズ (.msp) ファイルに保存します。 そのファイルをネットワーク インストール ポイントの Updates フォルダーに配置します。 Office をインストールするときに、セットアップは Updates フォルダーのセットアップ カスタマイズ ファイルを検索し、カスタマイズ内容を適用します。 Updates フォルダーは、Office 2013 の最初のインストール中にソフトウェアの更新プログラムを展開するためにのみ使用できます。

OCT はセットアップの一部で、ボリューム ライセンス版の製品に含まれています。 Office 2013 のソースファイルが`setup.exe /admin`含まれているネットワークインストールポイントのルートからコマンドラインを入力して、OCT を実行します。 たとえば、次のようなコマンドを使用します。

`\\server\share\Office15\setup.exe /admin`

管理者は OCT を使用してセットアップ カスタマイズ (.msp) ファイルを作成します。 Microsoft Office 2010 10 月の場合、管理者は次の領域をカスタマイズすることができます。

  - **セットアップ**クライアントと既定の組織名、追加のネットワークインストールソース、プロダクトキー、エンドユーザーライセンス契約、表示レベル、以前のバージョンの Office を削除するための既定のインストール場所を指定するために使用されます。インストール、セキュリティ設定、セットアッププロパティ。

  - **機能**ユーザー設定を構成し、Office 機能のインストール方法をカスタマイズするために使用されます。 管理者は、OCT を使用して、ユーザーの Office アプリケーション設定の初期既定値を指定することができます。 ユーザーはインストール後にほとんどの設定を変更できます。

  - **追加コンテンツ**ファイルを追加または削除したり、レジストリエントリを追加または削除したり、ショートカットを構成したりするために使用されます。

  - **Outlook**ユーザーの既定の Outlook プロファイルのカスタマイズ、Exchange 設定の指定、アカウントの追加、アカウントの削除と設定のエクスポート、\\送信受信グループの指定を行うために使用されます。

OCT の詳細については<http://go.microsoft.com/fwlink/p/?linkid=267516>、を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

