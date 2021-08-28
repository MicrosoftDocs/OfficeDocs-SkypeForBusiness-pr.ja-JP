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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015 トポロジの変更またはプロビジョニングを行い、ユーザーがストレスとパフォーマンス ツールを正常に実行できます。
ms.openlocfilehash: 224a2c1afde71ce94b69826ee0222dce729d22d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611916"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング
 
Skype for Business Server 2015 トポロジの変更またはプロビジョニングを行い、ユーザーがストレスとパフォーマンス ツールを正常に実行できます。
  
Skype for Business Server 2015 の展開に関する既存の設定と構成によっては、環境にいくつかの変更を加える必要がある場合があります。 これらの変更の一覧を次に示します。
  
1. 実行ポリシー Windows PowerShell制限されていないに設定します。 現在設定されている設定が不明な場合は、管理シェルを開き、Skype for Business Serverコマンドを実行できます。
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   値 Unrestricted が返されない場合は、次にこれを実行する必要があります。
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. サーバーを効果的にSkype for Business Serverするには、次の手順を実行する必要があります。
    
    - 2015 Skype for Business Serverトポロジ (コンピューター名、サービス インスタンス、サイト名、ポリシーなど) を理解してください。
    
    - 応答グループ ハント グループ (SIP URI など) など、グループに作成された一部のユーザーを割り当てる。
    
3. コマンド ラインからスクリプトを実行するには、次のコマンドを使用できます。
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 通常、このパッケージからスクリプトを実行した後、結果のトレースは、スクリプトが実行された場所と同じパス内のファイルに格納されます。 名前付け形式もあります \<scriptname\> 。$h$m$s.txt。 そのため、午後 12:15 ArchivingPolicy.ps1を実行した場合は、この名前のログ ファイルがArchivingPolicy121500.txt。
    
5. サーバー構成のこれらの例を提供しますが、ロード テストの実行が完了したら、構成を変更して復元またはロールバックする必要があります。
    

