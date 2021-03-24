---
title: Windows PowerShell Skype for Business Server 管理ツール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: Skype for Business Server では、管理ツールは、次の方法でWindows PowerShell。 Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。 Skype for Business Server ツールは、次のWindows PowerShell使用して実装されます。
ms.openlocfilehash: 61f5acdacc1a401a3541ba9d08213ad7f054374a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104203"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell Skype for Business Server 管理ツール
 
Skype for Business Server では、管理ツールは、次の方法でWindows PowerShell。 Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。 Skype for Business Server ツールは、次のWindows PowerShell使用して実装されます。 
  
- **トポロジ ビルダー**. トポロジ ビルダーを使用して、計画されたトポロジを作成、調整、および公開し、サーバーのインストールを開始する前にトポロジを検証します。 Skype for Business Server を個々のサーバーにインストールすると、サーバーはインストール プロセスの一環として公開されたトポロジを読み取り、インストール プログラムはトポロジの指示に基いてサーバーを展開します。 セットアップ後、構成情報は自動的にすべてのサーバーにレプリケートされます。 コンポーネントを展開に追加できるのは、トポロジ ビルダーを使用する場合のみです。
    
- **Skype for Business Server Management Shell**. Skype for Business Server 管理シェルを使用して、展開の完全なコマンド ライン管理を行います。
    
- **Skype for Business Server コントロール パネル**. Skype for Business Server コントロール パネル のユーザー インターフェイスを使用して、展開で最も一般的なタスクを管理できます。
    
これらのツールでは、約 550 個の製品固有のコマンドレットを含めて、Windows PowerShell コマンドレットを使用して展開を管理します。 Skype for Business Server に含まれるセキュリティ コマンドレットは、主に認証、およびユーザーの権限とアクセス許可を管理するために使用されます。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、多数のコマンドレットを使用すると、新しい Role-Based アクセス制御 (RBAC) 機能を使用して、Skype for Business Server の管理制御を委任できます。 Skype for Business Server コマンドレットの詳細については [、「Skype for Business Server Management Shell」を参照してください](../../manage/management-shell.md)。
  
Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能は、ユーザーが簡単に、または知らないうちにスクリプトを実行できない環境を作成することを目的としています。 既定では、Windows PowerShell のセキュリティ機能は有効です。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、「スクリプト セキュリティ [Windows PowerShellを参照してください](/previous-versions/msdn10/gg261722(v=msdn.10))。
