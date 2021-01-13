---
title: ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: ユーザーが Stress and Performance ツールを正常に実行できる Skype for Business Server 2015 トポロジの変更またはプロビジョニング。
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814937"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング
 
ユーザーが Stress and Performance ツールを正常に実行できる Skype for Business Server 2015 トポロジの変更またはプロビジョニング。
  
Skype for Business Server 2015 の展開に関する既存の設定と構成によっては、環境に変更を加える必要がある場合があります。 これらの変更の一覧を次に示します。
  
1. 実行ポリシー Windows PowerShell制限のないポリシーに設定します。 現在設定されている内容が不明な場合は、Skype for Business Server 管理シェルを開き、次のコマンドを実行できます。
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   値 Unrestricted が返されない場合は、次に実行する必要があります。
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Skype for Business Server を効果的に構成するには、次の手順を実行する必要があります。
    
    - Skype for Business Server 2015 トポロジ (コンピューター名、サービス インスタンス、サイト名、ポリシーなど) に精通している。
    
    - 応答グループ ハント グループ (SIP URI など) など、グループに作成されたユーザーの一部を割り当てる。
    
3. コマンド ラインからスクリプトを実行するには、次のコマンドを使用できます。
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 通常、このパッケージからスクリプトを実行した後、結果のトレースは、スクリプトが実行されたパスと同じパスにあるファイルに格納されます。 名前付け形式も \<scriptname\> $h$m$s.txt。 そのため、このArchivingPolicy.ps1 12:15 PM に実行した場合は、ArchivingPolicy121500.txt という名前のログ ファイルが表示ArchivingPolicy121500.txt。
    
5. サーバー構成の例を示しますが、ロード テストの実行が完了したら、構成の変更と復元またはロールバックの両方を行う必要があります。
    

