---
title: ビジネス サーバーの Skype のフロント エンド サーバーを管理します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: は、追加、削除、修正プログラム、またはビジネス サーバーの Skype でのフロント エンド サーバーを更新する方法を説明します。'
ms.openlocfilehash: bfd090ab007523ff05795aff012e4a01da4a0175
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026182"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>ビジネス サーバーの Skype のフロント エンド サーバーを管理します。
 
追加またはフロント エンド サーバーを削除する方法について説明しを適用する方法を更新または修正プログラムのフロント エンド サーバーにします。

## <a name="add-or-remove-front-end-servers"></a>追加またはフロント エンド サーバーを削除します。
  
プールにフロント エンド サーバーを追加またはプールからフロント エンド サーバーを削除すると、ときに、プールを再起動する必要があります。 
  
> [!IMPORTANT]
> トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。 
  
追加またはサーバーをフロント エンド サーバーを削除するときは、次の手順を使用することができます。
  
> [!NOTE]
> プールに新しいサーバーを追加する場合、累積的な更新プログラムがプール内の既存のサーバーと同じレベルになるように、新しいプール サーバーを更新します。 
  
### <a name="to-add-or-remove-front-end-servers"></a>追加またはフロント エンド サーバーを削除するには

1. 任意のフロント エンド サーバーを削除する場合は、まず、これらのサーバーへの新しい接続を停止します。 これを実行するには、次のコマンドレットを使用できます。
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. トポロジ ビルダーを開き、追加または必要なサーバーを削除します。 
    
3. トポロジを公開します。
    
    > [!IMPORTANT]
    > トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。 
  
  > [!NOTE]
> 追加プールにサーバーを削除すると、する必要がありますビジネス サーバーの展開ウィザードを追加する各コンピューターで、Skype を実行または削除するには、詳細についてを参照してください[Skype にインストール](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. 次のコマンドレットを入力して、プールが、リセット、フロント エンド プール内の次の方法のいずれかのサーバーの数を変更した場合: リセット ・ CsPoolRegistrarState ・ ResetType ・ FullReset ・ PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 台から任意の数
    
     - 任意の数から 2 台
    
     - 3 台から任意の数
    
     - 任意の数から 3 台
    
5. 以下のコマンドレットを入力してプールを再起動します。
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>フロントエンド サーバーのパッチまたは更新

フロント エンド プール内のサーバーにパッチを適用するときは、同時に、1 つのサーバーを行います。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>プール内のフロントエンド サーバーにアップグレードを適用する

1. 次のコマンドレットを入力します。
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     このコマンドレットで不足しているレプリカが示された場合は、次のコマンドレットでプールを復元してから、パッチを適用してください。
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. パッチを適用する最初のサーバーで、次のコマンドレットを実行します。
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    このコマンドレットでは、すべてのサービスを他のプール内のフロント エンド サーバーに移動し、このサーバーは、オフラインです。
    
3. このサーバーにアップグレードまたはパッチを適用します。
    
4. アップグレードしたサーバーで、次のコマンドレットを実行します。
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    サーバーがサービスに復帰します。
    
5. アップグレードが必要なサーバーごとに、手順 2 ～ 4 を繰り返します。
    
