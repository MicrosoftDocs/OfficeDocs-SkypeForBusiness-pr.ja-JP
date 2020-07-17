---
title: Skype for Business Server でのフロントエンドサーバーの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: Skype for Business Server でフロントエンドサーバーを追加、削除、修正、または更新する方法について説明します。'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098415"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Skype for Business Server でのフロントエンドサーバーの管理
 
この記事では、フロントエンドサーバーを追加または削除する方法と、フロントエンドサーバーにアップグレードまたはパッチを適用する方法について説明します。

  > [!NOTE]
> Skype for Business Server 2019 は、2台のフロントエンドサーバーを持つ Enterprise Edition フロントエンドプールをサポートしていません。このシナリオでは、トポロジを公開することはできません。

## <a name="add-or-remove-front-end-servers"></a>フロントエンドサーバーの追加または削除
  
フロントエンド サーバーをプールに追加したり、フロントエンド サーバーをプールから削除した場合は、プールを再起動する必要があります。 
  
> [!IMPORTANT]
> トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。 サーバーが再起動している間はプールがオフラインになり、そのプールに接続しているユーザーのサービスが中断されます。 ユーザーにサービスが中断されないようにするには、営業時間外にプール内の新しいサーバーでトポロジを公開するように計画します。 
  
フロントエンドサーバーを追加または削除する際には、次の手順を使用できます。
  
> [!NOTE]
> プールに新しいサーバーを追加している場合は、プール内の既存のサーバーと同じ累積更新レベルになるように、新しいプールサーバーを更新します。 
  
### <a name="to-add-or-remove-front-end-servers"></a>フロントエンドサーバーを追加または削除するには

1. フロントエンド サーバーを削除する場合、最初にこれらのサーバーへの新しい接続を停止します。これを実行するには、次のコマンドレットを使用できます。
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. トポロジ ビルダーを開き、必要なサーバーを追加または削除します。 
    
3. トポロジを公開します。
    
    > [!IMPORTANT]
    > トポロジ内のプールにサーバーを追加または削除し、更新されたトポロジを公開すると、プール内のすべてのサーバーが同時に再起動されます。 サーバーが再起動している間はプールがオフラインになり、そのプールに接続しているユーザーのサービスが中断されます。 ユーザーにサービスが中断されないようにするには、営業時間外にプール内の新しいサーバーでトポロジを公開するように計画します。 
  
  > [!NOTE]
> また、プールにサーバーを追加または削除する場合は、追加または削除した各コンピューターで Skype for business Server 展開ウィザードを実行する必要があります。詳細については、「 [Install skype For Business server on server on トポロジ」](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)を参照してください。
  
4. フロントエンドプール内のサーバーの数を次のいずれかの方法で変更した場合は、次のコマンドレットを入力して、プールをリセットします。 Reset-cspoolregistrarstate-ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2から任意
    
     - 任意の2
    
     - 3から任意の
    
     - 任意の3
    
5. 次のコマンドレットを入力して、プールを再起動します。
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>フロントエンドサーバーのパッチまたは更新

フロントエンドプール内のサーバーに修正プログラムを適用する場合は、一度に1台のサーバーを使用します。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>プール内のフロントエンドサーバーにアップグレードを適用するには

1. 次のコマンドレットを入力します。
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     このコマンドレットで不足しているレプリカが表示された場合は、次のコマンドレットを実行して、更新プログラムを適用する前にプールを回復します。
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 最初に修正プログラムを適用するサーバーで、次のコマンドレットを実行します。
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    このコマンドレットは、すべてのサービスをプール内の他のフロントエンドサーバーに移動し、このサーバーをオフラインにします。
    
3. このサーバーにアップグレードまたはパッチを適用します。
    
4. アップグレードされたサーバーで、次のコマンドレットを実行します。
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    サーバーがサービスに返されます。
    
5. アップグレードが必要な各サーバーについて、手順2-4 を繰り返します。
    
