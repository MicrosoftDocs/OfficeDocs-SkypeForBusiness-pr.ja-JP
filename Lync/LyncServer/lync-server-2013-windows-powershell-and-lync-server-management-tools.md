---
title: 'Lync Server 2013: Windows PowerShell および Lync Server 管理ツール'
description: 'Lync Server 2013: Windows PowerShell および Lync Server 管理ツール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546043"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell および Lync Server 2013 の管理ツール

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-07-20_

Microsoft Lync Server 2013 では、管理ツールは Windows PowerShell を使用して実装されます。 Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。 Windows PowerShell を使用して実装された Lync Server 2013 のツールには、次のものがあります。

  - **トポロジビルダー**。 トポロジビルダーを使用して、計画されたトポロジを作成、調整、および発行し、サーバーのインストールを開始する前にトポロジを検証します。 個別のサーバーに Lync Server 2013 をインストールすると、サーバーはインストールプロセスの一環として公開されたトポロジを読み取り、インストールプログラムはトポロジ内で指示されたとおりにサーバーを展開します。 セットアップの後、構成情報は自動的にすべてのサーバーにレプリケートされます。 コンポーネントは、トポロジビルダーを使用してのみ展開に追加できます。

  - **Lync Server 管理シェル**。 Lync Server 管理シェルを使用して、展開の完全なコマンドライン管理を行うことができます。

  - **Lync Server コントロールパネル**。 Microsoft Lync Server 2013 コントロールパネルのユーザーインターフェイスを使用して、展開で最も一般的なタスクを管理できます。

これらのツールでは、約 550 個の製品固有のコマンドレットを含めて、Windows PowerShell コマンドレットを使用して展開を管理します。 Lync Server 2013 に含まれているセキュリティコマンドレットは、主に認証を管理するため、およびユーザー権限とアクセス許可を管理するために使用されます。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 また、いくつかのコマンドレットを使用すると、新しい Role-Based アクセス制御 (RBAC) 機能を使用して Lync Server 2013 の管理制御を委任できます。 Lync Server コマンドレットの詳細については、「 [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)」を参照してください。

Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能は、ユーザーが簡単に、または知らないうちにスクリプトを実行できない環境を作成することを目的としています。 既定では、Windows PowerShell のセキュリティ機能は有効です。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、「Windows PowerShell スクリプトのセキュリティ」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) 。

</div>

<span> </span>

</div>

</div>

</div>

