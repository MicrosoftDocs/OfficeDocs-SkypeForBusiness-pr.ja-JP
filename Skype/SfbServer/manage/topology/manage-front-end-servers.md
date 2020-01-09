---
title: Skype for Business Server でフロントエンドサーバーを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: Skype for Business Server でフロントエンドサーバーを追加、削除、更新、または更新する方法について説明します。'
ms.openlocfilehash: 3689b869ba715f431ebcf0b537b4106a66177c62
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991532"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Skype for Business Server でフロントエンドサーバーを管理する
 
この記事では、フロントエンドサーバーを追加または削除する方法と、フロントエンドサーバーにアップグレードまたは更新プログラムを適用する方法について説明します。

## <a name="add-or-remove-front-end-servers"></a>フロントエンドサーバーを追加または削除する
  
フロントエンドサーバーをプールに追加する場合、またはプールからフロントエンドサーバーを削除する場合は、プールを再起動する必要があります。 
  
> [!IMPORTANT]
> トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。 
  
フロントエンドサーバーを追加または削除するときには、次の手順を使用できます。
  
> [!NOTE]
> プールに新しいサーバーを追加する場合、累積的な更新プログラムがプール内の既存のサーバーと同じレベルになるように、新しいプール サーバーを更新します。 
  
### <a name="to-add-or-remove-front-end-servers"></a>フロントエンドサーバーを追加または削除するには

1. フロントエンドサーバーを削除する場合は、まず、それらのサーバーへの新しい接続を停止します。 これを実行するには、次のコマンドレットを使用できます。
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. トポロジビルダーを開き、必要なサーバーを追加または削除します。 
    
3. トポロジを公開します。
    
    > [!IMPORTANT]
    > トポロジ内のプールにサーバーを追加、またはそこから削除し、更新したトポロジを公開すると、プール内のすべてのサーバーが同時に再起動します。サーバーが再起動する間、プールはオフラインです。プールに接続しているユーザーに対するサービスは中断されます。ユーザーへのサービスの中断を防ぐため、プール内で新しいサーバーを設定したトポロジは、営業時間外に公開するように計画します。 
  
  > [!NOTE]
> また、プールにサーバーを追加または削除する場合は、追加または削除された各コンピューターで Skype for Business Server 展開ウィザードを実行する必要があります。詳細については、「[トポロジのサーバーに skype for Business server をインストール](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)する」を参照してください。
  
4. フロントエンドプール内のサーバーの数を次のいずれかの方法で変更した場合は、次のコマンドレットを入力してプールをリセットします。 CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 台から任意の数
    
     - 任意の数から 2 台
    
     - 3 台から任意の数
    
     - 任意の数から 3 台
    
5. 以下のコマンドレットを入力してプールを再起動します。
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>フロントエンド サーバーのパッチまたは更新

フロントエンドプールにサーバーを修正する場合は、一度に1つのサーバーを実行します。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>プール内のフロントエンド サーバーにアップグレードを適用する

1. 次のコマンドレットを入力します。
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     このコマンドレットで不足しているレプリカが示された場合は、次のコマンドレットでプールを復元してから、パッチを適用してください。
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. パッチを適用する最初のサーバーで、次のコマンドレットを実行します。
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    このコマンドレットは、すべてのサービスをプール内の他のフロントエンドサーバーに移動し、このサーバーをオフラインにします。
    
3. このサーバーにアップグレードまたはパッチを適用します。
    
4. アップグレードしたサーバーで、次のコマンドレットを実行します。
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    サーバーがサービスに復帰します。
    
5. アップグレードが必要なサーバーごとに、手順 2 ～ 4 を繰り返します。
    
