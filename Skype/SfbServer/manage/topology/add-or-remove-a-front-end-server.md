---
title: 追加または Skype のビジネス サーバーのフロント エンド サーバーを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '概要: は、追加または、Skype のビジネス サーバーのフロント エンド サーバーを削除する方法を説明します。'
ms.openlocfilehash: 07f23f3dfb913a353a72ac855915d4001ed02f24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018784"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server"></a>追加または Skype のビジネス サーバーのフロント エンド サーバーを削除します。
 
**の概要:** 追加または Skype のビジネス サーバーのフロント エンド サーバーを削除する方法について説明します。
  
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