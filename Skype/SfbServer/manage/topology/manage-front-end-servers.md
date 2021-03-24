---
title: Skype for Business Server でフロントエンド サーバーを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: Skype for Business Server のフロント エンド サーバーを追加、削除、修正、または更新する方法について学習します。'
ms.openlocfilehash: 24527a5f973b21c35e386f0565ac6deb69e15070
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103193"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Skype for Business Server でフロントエンド サーバーを管理する
 
この記事では、フロントエンド サーバーを追加または削除する方法、およびフロントエンド サーバーにアップグレードまたはパッチを適用する方法について説明します。

  > [!NOTE]
> Skype for Business Server 2019 は、2 台のフロント エンド サーバーを持つ Enterprise Edition フロントエンド プールをサポートしていないので、そのシナリオではトポロジを公開できません。

## <a name="add-or-remove-front-end-servers"></a>フロントエンド サーバーを追加または削除する
  
フロントエンド サーバーをプールに追加したり、フロントエンド サーバーをプールから削除した場合は、プールを再起動する必要があります。 
  
> [!IMPORTANT]
> トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。 サーバーがプールを再起動している間はオフラインで、そのプールに接続されているユーザーのサービスが中断されます。 ユーザーへのサービスの中断を防ぐには、非営業時間内にプール内の新しいサーバーでトポロジを公開する計画を立てします。 
  
フロント エンド サーバーを追加または削除する場合は、次の手順を使用できます。
  
> [!NOTE]
> プールに新しいサーバーを追加する場合は、新しいプール サーバーをプール内の既存のサーバーと同じ累積的な更新レベルに更新します。 
  
### <a name="to-add-or-remove-front-end-servers"></a>フロントエンド サーバーを追加または削除するには

1. フロントエンド サーバーを削除する場合、最初にこれらのサーバーへの新しい接続を停止します。これを実行するには、次のコマンドレットを使用できます。
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. トポロジ ビルダーを開き、必要なサーバーを追加または削除します。 
    
3. トポロジを公開します。
    
    > [!IMPORTANT]
    > トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。 サーバーがプールを再起動している間はオフラインで、そのプールに接続されているユーザーのサービスが中断されます。 ユーザーへのサービスの中断を防ぐには、非営業時間内にプール内の新しいサーバーでトポロジを公開する計画を立てします。 
  
  > [!NOTE]
> また、プールにサーバーを追加または削除する場合は、追加または削除された各コンピューターで Skype for Business Server 展開ウィザードを実行する必要があります。詳細については、「トポロジ内のサーバーに[Skype for Business Server](../../deploy/install/install-skype-for-business-server.md)をインストールする」を参照してください。
  
4. 次の方法でフロントエンド プール内のサーバーの数を変更した場合は、次のコマンドレットを入力してプールをリセットします。Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 ~ any
    
     - Any ~ 2
    
     - 3 ~ any
    
     - Any ~ 3
    
5. 次のコマンドレットを入力してプールを再起動する
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>フロント エンド サーバーにパッチを適用または更新する

フロントエンド プール内のサーバーにパッチを適用する場合は、一度に 1 つのサーバーを適用します。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>プール内のフロントエンド サーバーにアップグレードを適用するには

1. 次の cmdlet を入力します。
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     このコマンドレットに不足しているレプリカが表示される場合は、次のコマンドレットを実行してプールを回復してから、パッチを適用します。
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. パッチを適用する最初のサーバーで、次のコマンドレットを実行します。
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    このコマンドレットは、すべてのサービスをプール内の他のフロントエンド サーバーに移動し、このサーバーをオフラインにします。
    
3. このサーバーにアップグレードまたはパッチを適用します。
    
4. アップグレードされたサーバーで、次のコマンドレットを実行します。
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    サーバーはサービスに返されます。
    
5. アップグレードする必要があるサーバーごとに、手順 2 ~ 4 を繰り返します。
