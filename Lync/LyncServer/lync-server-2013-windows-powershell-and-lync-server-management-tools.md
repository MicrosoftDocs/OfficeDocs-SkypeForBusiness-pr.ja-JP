---
title: 'Lync Server 2013: Windows PowerShell と Lync Server の管理ツール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell と Lync Server 2013 の管理ツール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-07-20_

Microsoft Lync Server 2013 では、管理ツールは Windows PowerShell を使って実装されています。 Windows PowerShell には、コマンドライン環境、製品固有のコマンド、完全なスクリプト言語が含まれています。 Windows PowerShell を使用して実装されている Lync Server 2013 ツールには、次のようなものがあります。

  - **トポロジビルダー**。 トポロジビルダーを使用して、計画されたトポロジを作成、調整、および公開し、サーバーのインストールを開始する前にトポロジを検証します。 個々のサーバーに Lync Server 2013 をインストールすると、サーバーはインストールプロセスの一環として公開されたトポロジを読み取り、インストールプログラムはトポロジで指示されたとおりにサーバーを展開します。 After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.

  - **Lync Server 管理シェル**。 Lync Server 管理シェルを使用すると、展開の完全なコマンドライン管理を行うことができます。

  - **Lync Server コントロールパネル**。 Microsoft Lync Server 2013 コントロールパネルのユーザーインターフェイスを使用して、展開で最も一般的なタスクを管理することができます。

これらのツールは、550製品固有のコマンドレットを閉じるなど、展開を管理するための Windows PowerShell コマンドレットを使用します。 Lync Server 2013 に含まれているセキュリティコマンドレットは、主に認証、ユーザー権利、アクセス許可を管理するために使用されます。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、いくつかのコマンドレットを使用して、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して、Lync Server 2013 の管理制御を委任することができます。 Lync Server のコマンドレットの詳細については、「 [Lync server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」を参照してください。

Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能は、ユーザーが簡単にスクリプトを実行することができない環境を作成することを目的としています。 既定では、Windows PowerShell のセキュリティ機能は有効になっています。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、「Windows PowerShell [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)スクリプトのセキュリティ」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

