---
title: 障害復旧用にペアのフロント エンド プールを展開Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: ペアのフロント エンド プールを使用して障害復旧保護を提供する場合がありますが、これは要件ではありません。
ms.openlocfilehash: 9c56ad7a0af5b50f4843a84205c48a11a9177a47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608574"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>障害復旧用にペアのフロント エンド プールを展開Skype for Business Server
 
ペアのフロント エンド プールを使用して障害復旧保護を提供する場合がありますが、これは要件ではありません。
  
トポロジ ビルダーを使用して、ペアのフロントエンド プールの障害復旧トポロジを簡単に展開できます。 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>ペアのフロントエンド プールを展開するには

1. プールが新規でまだ定義されていない場合は、トポロジ ビルダーを使用してプールを作成します。
    
2. トポロジ ビルダーで、2 つのプールのいずれかを右クリックし、[プロパティの編集] **をクリックします**。
    
3. 左ウィンドウの [**復元**] をクリックし、右ウィンドウの [**関連付けられているバックアップ プール**] を選択します。
    
4. [**関連付けられているバックアップ プール**] の下のボックスで、このプールとペアにするプールを選択します。別のプールとペアでない既存のプールのみ選択できます。
    
5. [**音声の自動フェールオーバーとフェールバック**] を選択し、[**OK**] をクリックします。
    
    このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの [**復元**] の下に表示されます。 
    
6. トポロジ ビルダーを使用してトポロジを発行します。
    
7. 2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。 この手順の最後の手順は省略できます。
    
    ただし、ペア関係を定義する前にプールが既に展開されている場合は、次の最終手順を完了する必要があります。
    
8. 両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。
    
9. ブートストラップが両方のプールのすべてのフロントエンド サーバーにバックアップ ペアリングに必要なコンポーネントのインストールを完了したら、両方のプールでこれらのフロント エンド サーバーに以前に適用された既存の累積的な更新プログラムを再適用し、次の手順に進みます。

10. 管理シェルSkype for Business Serverコマンド プロンプトから、次のコマンドを実行します。 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. 次のコマンドレットを使用して、両方のプールのユーザーデータと会議データを強制的に同期します。
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    データの同期には時間がかかる場合があります。 次のコマンドレットを使用して、状態を確認できます。 両方向の状態が定常状態にあるか確認します。
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> [ **音声の自動** フェールオーバーとフェールバック] オプションとトポロジ ビルダーの関連付けられた時間間隔は、Lync Server で導入された音声復元機能にのみ適用されます。 このオプションを選択しても、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。 プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。
  
## <a name="see-also"></a>関連項目

[フロントエンド プールの障害復旧 (Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
