---
title: Windows PowerShell と Skype for Business Server 管理ツール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: Skype for Business Server では、管理ツールは Windows PowerShell を使って実装されています。 Windows PowerShell には、コマンドライン環境、製品固有のコマンド、完全なスクリプト言語が含まれています。 Windows PowerShell を使用して実装されている Skype for Business Server ツールには、次のようなものがあります。
ms.openlocfilehash: 3eb156e002603378ec77fbbcbde4772870aad907
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296883"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell と Skype for Business Server 管理ツール
 
Skype for Business Server では、管理ツールは Windows PowerShell を使って実装されています。 Windows PowerShell には、コマンドライン環境、製品固有のコマンド、完全なスクリプト言語が含まれています。 Windows PowerShell を使用して実装されている Skype for Business Server ツールには、次のようなものがあります。 
  
- **トポロジビルダー**。 トポロジビルダーを使用して、計画されたトポロジを作成、調整、および公開し、サーバーのインストールを開始する前にトポロジを検証します。 個々のサーバーに Skype for Business Server をインストールすると、サーバーはインストールプロセスの一環として公開されたトポロジを読み取り、インストールプログラムはトポロジで指示されたとおりにサーバーを配置します。 After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Skype For Business Server 管理シェル**。 Skype for Business Server 管理シェルを使って、展開の完全なコマンドライン管理を行うことができます。
    
- **Skype For Business Server コントロールパネル**。 Skype for Business Server コントロールパネルのユーザーインターフェイスを使用して、展開で最も一般的なタスクを管理することができます。
    
これらのツールは、550製品固有のコマンドレットを閉じるなど、展開を管理するための Windows PowerShell コマンドレットを使用します。 Skype for Business Server に含まれているセキュリティコマンドレットは、主に認証、ユーザー権利、アクセス許可を管理するために使用されます。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、いくつかのコマンドレットを使用して、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して、Skype for Business Server の管理制御を委任することができます。 Skype for Business Server コマンドレットの詳細については、「Skype for business [Server 管理シェル](../../manage/management-shell.md)」を参照してください。
  
Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能は、ユーザーが簡単にスクリプトを実行することができない環境を作成することを目的としています。 既定では、Windows PowerShell のセキュリティ機能は有効になっています。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、「 [Windows PowerShell スクリプトのセキュリティ](https://go.microsoft.com/fwlink/p/?LinkId=213145)」を参照してください。
  

