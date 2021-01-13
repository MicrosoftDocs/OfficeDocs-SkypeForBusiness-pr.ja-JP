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
description: Skype for Business Server では、管理ツールは管理ツールを使用してWindows PowerShell。 Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。 この機能を使用して実装される Skype for Business Server ツールにはWindows PowerShell次のものが含まれます。
ms.openlocfilehash: 740a5e3d7998523970e1b0adc1e72aa85d0b09c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832157"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell Skype for Business Server 管理ツール
 
Skype for Business Server では、管理ツールは管理ツールを使用してWindows PowerShell。 Windows PowerShell には、コマンド ライン環境、製品固有のコマンド、およびすべてのスクリプト言語が含まれています。 この機能を使用して実装される Skype for Business Server ツールにはWindows PowerShell次のものが含まれます。 
  
- **トポロジ ビルダー**。 トポロジ ビルダーを使用して計画したトポロジを作成、調整、および公開し、サーバーのインストールを開始する前にトポロジを検証します。 Skype for Business Server を個々のサーバーにインストールすると、サーバーはインストール プロセスの一環として公開されたトポロジを読み取り、インストール プログラムはトポロジに指示されたサーバーを展開します。 セットアップ後、構成情報は自動的にすべてのサーバーにレプリケートされます。 トポロジ ビルダーを使用する場合にのみ、展開にコンポーネントを追加できます。
    
- **Skype for Business Server 管理シェル**。 展開の完全なコマンドライン管理には、Skype for Business Server 管理シェルを使用できます。
    
- **Skype for Business Server コントロール パネル**。 Skype for Business Server コントロール パネルのユーザー インターフェイスを使用して、展開内の最も一般的なタスクを管理できます。
    
これらのツールでは、約 550 個の製品固有のコマンドレットを含めて、Windows PowerShell コマンドレットを使用して展開を管理します。 Skype for Business Server に含まれるセキュリティ コマンドレットは、主に認証、およびユーザー権限とアクセス許可を管理するために使用されます。 認証の管理には、さまざまなコマンドレット (証明書と暗証番号 (PIN) の認証用のコマンドレットなど) を使用できます。 さらに、多くのコマンドレットを使用すると、新しい Role-Based アクセス制御 (RBAC) 機能を使用して、Skype for Business Server の管理制御を委任できます。 Skype for Business Server コマンドレットの詳細については [、「Skype for Business Server Management Shell」を参照してください](../../manage/management-shell.md)。
  
Windows PowerShell のスクリプト セキュリティ機能は、Microsoft Visual Basic Scripting Edition (VBScript) など、古いテクノロジにおけるスクリプト関連のいくつかのセキュリティ問題を回避するように特別に設計されています。 Windows PowerShell のセキュリティ機能は、ユーザーが簡単に、または知らないうちにスクリプトを実行できない環境を作成することを目的としています。 既定では、Windows PowerShell のセキュリティ機能は有効です。 これらの機能の状態は、スクリプトに関するニーズと多様なセキュリティの目標に応じて変更できます。 シェルによってユーザーがスクリプトを実行できないようにするというわけではありません。 あくまでも、ユーザー自身がスクリプトを実行しているという認識を持たずにスクリプトを実行することを、既定で困難にするということです。 詳細については、「スクリプト セキュリティ [Windows PowerShell参照してください](https://go.microsoft.com/fwlink/p/?LinkId=213145)。
  

