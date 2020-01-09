---
title: ストレスとパフォーマンスのシナリオでのロードを実行するためのトポロジのプロビジョニング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015 のトポロジの変更またはプロビジョニングを行うと、ユーザーはストレスとパフォーマンスのツールを正常に実行することができます。
ms.openlocfilehash: e58bfce5e618c6e62f272c0acb0b415cbb471d40
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992494"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>ストレスとパフォーマンスのシナリオでのロードを実行するためのトポロジのプロビジョニング
 
Skype for Business Server 2015 のトポロジの変更またはプロビジョニングを行うと、ユーザーはストレスとパフォーマンスのツールを正常に実行することができます。
  
Skype for Business Server 2015 の展開に関する既存の設定と構成によっては、お使いの環境にいくつかの変更を加える必要がある場合があります。 これらの変更の一覧を次に示します。
  
1. Windows PowerShell の実行ポリシーを無制限に設定します。 現在設定されている内容がわからない場合は、Skype for Business Server 管理シェルを開き、次のコマンドを実行します。
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   制限なしの値が返されない場合は、次の操作を実行する必要があります。
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Skype for Business Server を効果的に構成するには、次のことを行う必要があります。
    
    - Skype for Business Server 2015 トポロジ (コンピューター名、サービスインスタンス、サイト名、ポリシーなど) について理解している必要があります。
    
    - 応答グループのハントグループ (SIP Uri など) など、グループに作成されたユーザーの一部を割り当てます。
    
3. コマンドラインからスクリプトを実行するには、次のように使用できます。
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 通常、このパッケージからスクリプトを実行すると、スクリプトが実行された場所と同じパスのファイルに結果のトレースが格納されます。 \<Scriptname\>$h $ m $ s .txt という名前の書式もあります。 そのため、12:15 PM で ArchivingPolicy を実行すると、ArchivingPolicy121500 という名前のログファイルが表示されます。
    
5. これらの例は、サーバー構成のために用意されていますが、ロードテストの実行が完了したら、構成を変更し、復元またはロールバックすることをお勧めします。
    

