---
title: Windows PowerShellおよびSkype for Business Server管理ツール
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: このSkype for Business Server管理ツールは、管理ツールを使用Windows PowerShell。 Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。 Skype for Business Serverを使用して実装されるWindows PowerShellには、次のものが含まれます。
---

# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShellおよびSkype for Business Server管理ツール
 
このSkype for Business Server管理ツールは、管理ツールを使用Windows PowerShell。 Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。 Skype for Business Serverを使用して実装されるWindows PowerShellには、次のものが含まれます。 
  
- **トポロジ ビルダー**。 トポロジ ビルダーを使用して、計画されたトポロジを作成、調整、および公開し、サーバーのインストールを開始する前にトポロジを検証します。 個々のサーバーに Skype for Business Server をインストールすると、サーバーはインストール プロセスの一部として公開されたトポロジを読み取り、インストール プログラムはトポロジの指示に基いてサーバーを展開します。 セットアップ後、構成情報は自動的にすべてのサーバーにレプリケートされます。 コンポーネントを展開に追加できるのは、トポロジ ビルダーを使用する場合のみです。
    
- **Skype for Business Server管理シェル。** 展開の完全Skype for Business Server管理には、管理シェルを使用できます。
    
- **Skype for Business Serverコントロール パネル**。 コントロール パネルのユーザー Skype for Business Serverを使用して、展開で最も一般的なタスクを管理できます。
    
これらのツールでは、約 550 個の製品固有のコマンドレットを含めて、Windows PowerShell コマンドレットを使用して展開を管理します。 このセキュリティ コマンドレットは、Skype for Business Server、ユーザーの権限とアクセス許可を管理するために主に使用されます。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、多数のコマンドレットを使用すると、新しいアクセス制御 (RBAC) Role-Basedを使用して、管理者による管理制御を委任Skype for Business Server。 このコマンドレットの詳細についてはSkype for Business Server管理シェル[Skype for Business Server参照してください](../../manage/management-shell.md)。
  
Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能は、ユーザーが簡単に、または知らないうちにスクリプトを実行できない環境を作成することを目的としています。 既定では、Windows PowerShell のセキュリティ機能は有効です。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、「スクリプト セキュリティ[Windows PowerShell参照してください](/previous-versions/msdn10/gg261722(v=msdn.10))。
