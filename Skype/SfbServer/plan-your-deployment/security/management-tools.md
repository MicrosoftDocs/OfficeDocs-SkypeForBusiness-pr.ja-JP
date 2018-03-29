---
title: Windows PowerShell と Skype for Business Server 2015 の管理ツール
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: ビジネス サーバー 2015 の Skype は、管理ツールは Windows PowerShell を使用して実装されます。 Windows PowerShell には、コマンドライン環境、製品に固有のコマンド、および完全なスクリプト言語が含まれています。 Skype は、Windows PowerShell を使用して実装するビジネス サーバー 2015 ツールについては、次のとおりです。
ms.openlocfilehash: 25631ce7acf59567b431d7eebdf190c4b63d7913
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="windows-powershell-and-skype-for-business-server-2015-management-tools"></a>Windows PowerShell と Skype for Business Server 2015 の管理ツール
 
ビジネス サーバー 2015 の Skype は、管理ツールは Windows PowerShell を使用して実装されます。 Windows PowerShell には、コマンドライン環境、製品に固有のコマンド、および完全なスクリプト言語が含まれています。 Skype は、Windows PowerShell を使用して実装するビジネス サーバー 2015 ツールについては、次のとおりです。 
  
- **トポロジ ビルダー**です。 作成、調整、および、計画したトポロジを公開するのにはトポロジ ビルダーを使用して、サーバーへのインストールを開始する前にトポロジを検証します。 Skype をビジネス サーバー 2015 の個々 のサーバーにインストールすると、サーバーは、インストール プロセスの一部として公開されているトポロジを読み取るし、インストール プログラムは、トポロジで指示されたとおりにサーバーを展開します。 セットアップの後、構成情報はすべてのサーバーに自動的にレプリケートされます。 トポロジ ビルダーを使ってのみ、展開にコンポーネントを追加できます。
    
- **ビジネス サーバー管理シェルの Skype**です。 ビジネス サーバー管理シェルの Skype を使用するには、展開の完全なコマンド ラインの管理のため。
    
- **Skype**ビジネス サーバーのコントロール パネルのします。 ビジネス サーバーのコントロール パネルのユーザー インターフェイスの Skype を使用するには、配置の一般的なタスクを管理します。
    
これらのツールは、550 の製品固有のコマンドレットに近いなど、展開を管理するための Windows PowerShell コマンドレットを使用します。 ビジネス サーバー 2015 の Skype に含まれているセキュリティのコマンドレットは主に、認証、およびユーザー権利とアクセス許可を管理するために使用します。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、いくつかのコマンドレットでは、ビジネス サーバー 2015 の Skype の管理制御を委任するのには、新しいロール ベースのアクセス制御 (RBAC) 機能を使用する有効にします。 Skype ビジネス サーバー コマンドレットの詳細については、 [Skype](../../manage/management-shell.md)ビジネス サーバー 2015 の管理シェルを参照してください。
  
Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能をユーザーが簡単にできない環境を作成するためのものか知らないうちにスクリプトを実行します。 既定では、Windows PowerShell のセキュリティ機能が有効になります。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、 [Windows PowerShell スクリプトのセキュリティ](https://go.microsoft.com/fwlink/p/?LinkId=213145)を参照してください。
  

