---
title: Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。
ms.openlocfilehash: 73f7d7619efbfc82124507234ebea8ebbcf4a7e8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002907"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開
 
ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。
  
トポロジビルダーを使用すると、ペアリングされたフロントエンドプールの障害回復トポロジを簡単に展開できます。 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>フロント エンド プールのペアを展開するには

1. プールが新しく、まだ定義されていない場合は、トポロジビルダーを使用してプールを作成します。
    
2. トポロジビルダーで、2つのプールのいずれかを右クリックし、[**プロパティの編集**] をクリックします。
    
3. 左ウィンドウの **[復元]** をクリックし、右ウィンドウの **[関連付けられているバックアップ プール]** を選びます。
    
4. **[関連付けられているバックアップ プール]** の下のボックスで、このプールとペアにするプールを選択します。ペアでない単独の既存のプールのみを選ぶことができます。
    
5. **[音声の自動フェールオーバーとフェールバック]** を選択し、**[OK]** をクリックします。
    
    このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの **[復元]** の下に表示されます。 
    
6. トポロジビルダーを使用してトポロジを公開します。
    
7. 2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。 この手順の最後の手順はスキップできます。
    
    ただし、ペアのリレーションシップを定義する前に、プールを既に展開している場合は、次の最終的な手順を完了する必要があります。
    
8. 両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。
    
9. 両方のプールの各フロントエンドサーバー上のバックアップペアリングに必要なコンポーネントのインストールが完了したら、両方のプールの各フロントエンドサーバーに既に適用されていた既存の累積的な更新プログラムを再度適用してから、続行してください。次の手順を実行します。

10. Skype for Business Server Management Shell コマンドプロンプトから次のコマンドを実行します。 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. 次のコマンドレットを使用して、両方のプールのユーザーと会議のデータを相互に同期させる必要があります。
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    データの同期には時間がかかる場合があります。次のコマンドレットを使用して、状態を確認できます。両方向の状態が安定状態であることを確認します。
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> [**音声の自動フェールオーバー** ] オプションと [トポロジビルダー] の関連付けられた時間間隔は、Lync Server で導入された音声回復機能のみに適用されます。 このオプションを選んでも、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。 プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server のフロントエンドプールの障害回復](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
