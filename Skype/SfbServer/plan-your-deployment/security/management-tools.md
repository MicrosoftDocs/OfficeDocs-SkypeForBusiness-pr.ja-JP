---
title: Windows PowerShell と Skype ビジネス サーバー管理ツールの
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: ビジネス サーバーの Skype は、管理ツールは Windows PowerShell を使用して実装されます。 Windows PowerShell には、コマンドライン環境、製品に固有のコマンド、および完全なスクリプト言語が含まれています。 Windows PowerShell を使用して実装されているビジネスのサーバー ツールの Skype を以下に示します。
ms.openlocfilehash: 158664b4c0f83b7619c6a739046247bfdf495f37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897395"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell と Skype ビジネス サーバー管理ツールの
 
ビジネス サーバーの Skype は、管理ツールは Windows PowerShell を使用して実装されます。 Windows PowerShell には、コマンドライン環境、製品に固有のコマンド、および完全なスクリプト言語が含まれています。 Windows PowerShell を使用して実装されているビジネスのサーバー ツールの Skype を以下に示します。 
  
- **トポロジ ビルダー**です。 作成、調整、および、計画したトポロジを公開するのにはトポロジ ビルダーを使用して、サーバーへのインストールを開始する前にトポロジを検証します。 Skype をビジネス サーバーの個々 のサーバーにインストールすると、サーバーは、インストール プロセスの一部として公開されているトポロジを読み取るし、インストール プログラムは、トポロジで指示されたとおりにサーバーを展開します。 After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **ビジネス サーバー管理シェルの Skype**です。 ビジネス サーバー管理シェルの Skype を使用するには、展開の完全なコマンド ラインの管理のため。
    
- **Skype**ビジネス サーバーのコントロール パネルのします。 ビジネス サーバーのコントロール パネルのユーザー インターフェイスの Skype を使用するには、配置の一般的なタスクを管理します。
    
これらのツールは、550 の製品固有のコマンドレットに近いなど、展開を管理するための Windows PowerShell コマンドレットを使用します。 ビジネス サーバーの Skype に含まれているセキュリティのコマンドレットは主に、認証、およびユーザー権利とアクセス許可を管理するために使用します。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、コマンドレットの多くを使用すると、Business Server の Skype の管理制御を委任するのには、新しいロール ベースのアクセス制御 (RBAC) 機能を使用します。 Skype ビジネス サーバー コマンドレットの詳細については、 [Skype](../../manage/management-shell.md)ビジネス サーバー管理シェルを参照してください。
  
Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能をユーザーが簡単にできない環境を作成するためのものか知らないうちにスクリプトを実行します。 既定では、Windows PowerShell のセキュリティ機能が有効になります。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、 [Windows PowerShell スクリプトのセキュリティ](https://go.microsoft.com/fwlink/p/?LinkId=213145)を参照してください。
  

