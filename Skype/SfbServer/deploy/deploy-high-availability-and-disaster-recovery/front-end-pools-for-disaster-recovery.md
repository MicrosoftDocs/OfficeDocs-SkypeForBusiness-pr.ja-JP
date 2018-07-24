---
title: ビジネス サーバーの Skype での災害復旧のための一対のフロント エンド プールを展開します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。
ms.openlocfilehash: 72083b2ec249a83c06cd8ccebe683f29d15709e0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026482"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>ビジネス サーバーの Skype での災害復旧のための一対のフロント エンド プールを展開します。
 
ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。
  
トポロジ ビルダーを使用してペアのフロント エンド プールの災害復旧トポロジーを容易に展開できます。 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>フロント エンド プールのペアを展開するには

1. プールは新しいし、まだ定義されていない場合、プールを作成するのにはトポロジ ビルダーを使用します。
    
2. トポロジ ビルダーでは、2 つのプールでは、いずれかを右クリックし、**プロパティの編集**] をクリックします。
    
3. 左ウィンドウの **[復元]** をクリックし、右ウィンドウの **[関連付けられているバックアップ プール]** を選びます。
    
4. **[関連付けられているバックアップ プール]** の下のボックスで、このプールとペアにするプールを選択します。ペアでない単独の既存のプールのみを選ぶことができます。
    
5. **[音声の自動フェールオーバーとフェールバック]** を選択し、**[OK]** をクリックします。
    
    このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの **[復元]** の下に表示されます。 
    
6. トポロジ ビルダーを使用すると、トポロジを公開します。
    
7. 2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。最後の 2 つの手順を省略できます。
    
    しかし、ペアの関係を定義する前にプールが既に展開されていた場合は、次の 2 つの最終手順を実行する必要があります。
    
8. 両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。
    
9. ビジネス サーバー管理シェル コマンド プロンプトの Skype では、次を実行します。 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. 次のコマンドレットを実行して、両方のプールのユーザーおよび電話会議データが相互に同期されるようにします。
    
   ```
   Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
   ```

   ```
   Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
   ```

   データの同期には時間がかかる場合があります。次のコマンドレットを使用して、状態を確認できます。両方向の状態が安定状態であることを確認します。
    
   ```
   Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
   ```

   ```
   Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
   ```

> [!NOTE]
> **自動フェイル オーバーおよびフェイル バック音声**オプションおよびトポロジ ビルダーに関連付けられている時間間隔は、Lync Server で導入された音声の復元機能にのみ適用されます。 このオプションを選んでも、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。 プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。
  
## <a name="see-also"></a>関連項目

[ビジネス サーバーの前面の Skype で最後のプール災害復旧](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)