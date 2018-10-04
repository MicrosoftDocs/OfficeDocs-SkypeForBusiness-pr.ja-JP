---
title: ストレスおよびパフォーマンスのシナリオで負荷を実行するのにはトポロジの準備
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: ビジネス サーバー 2015 トポロジの変更やプロビジョニングのストレスおよびパフォーマンス ツールが正常に実行できるようにする Skype。
ms.openlocfilehash: 6ff08a3b99f4dc1f05b56c2a1fa86733ccf4f852
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373779"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>ストレスおよびパフォーマンスのシナリオで負荷を実行するのにはトポロジの準備
 
ビジネス サーバー 2015 トポロジの変更やプロビジョニングのストレスおよびパフォーマンス ツールが正常に実行できるようにする Skype。
  
既存の設定およびビジネス サーバー 2015 の Skype の配置の構成によっては、環境内の一部を変更する必要があります。 これらの変更の一覧は次のとおりです。
  
1. Windows PowerShell 実行ポリシーは、[制限しない] に設定します。 かわからないことが現時点に設定するは、ビジネス サーバー管理シェルには、Skype を開くし、このコマンドを実行します。
    
   ```
   Get-ExecutionPolicy
   ```

   [制限しない] の値が返されない場合は、次にこのを実行する必要があります。
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. 効果的なビジネス サーバーの Skype を構成するにする必要があります。
    
    - (コンピューター名、サービス インスタンス、サイト名、ポリシーなど) ビジネス サーバー 2015 トポロジの場合、Skype を理解します。
    
    - 応答のグループのハント グループ (たとえば、SIP Uri) など、一部のグループに作成されるユーザーを割り当てます。
    
3. コマンドラインからスクリプトを実行するには、次の使用できます。
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. 通常、スクリプトを実行すると、このパッケージからして、結果のトレースはスクリプトが実行された場所から同じパス内のファイルに保存されます。 名前付け形式を同様に、\<移動し、scriptname\>$h$m$s.txt。 午後 12時 15分、ArchivingPolicy.ps1 を実行すると、ArchivingPolicy121500.txt をという名前のログ ファイルが表示されます。
    
5. サーバー構成のこれらの例を提供してきました、両方の構成を変更し、復元またはロード テストの実行が終了したら後にロールバックするです。
    

