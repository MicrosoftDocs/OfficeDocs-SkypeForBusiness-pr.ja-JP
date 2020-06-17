---
title: 応答グループを移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Skype for Business Server 2019 プールに移動することが含まれます。 従来の応答グループを移行した後、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールによって処理されなくなりました。
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752679"
---
# <a name="migrate-response-groups"></a>応答グループを移行する

ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイルをコピーし、応答グループの連絡先オブジェクトを従来の展開から Skype for Business Server 2019 プールに移動することが含まれます。 従来の応答グループを移行した後、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールによって処理されなくなりました。
  
> [!NOTE]
> すべてのユーザーを Skype for Business Server 2019 プールに移動する前に、応答グループを移行することもできますが、すべてのユーザーを最初に移動することをお勧めします。 特に、応答グループのエージェントであるユーザーは、Skype for Business Server 2019 プールに移動するまで、新機能のすべての機能を利用できません。 
  
応答グループを移行する前に、応答グループアプリケーションを含む Skype for Business Server 2019 プールを展開しておく必要があります。 応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。 **ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。 
  
> [!NOTE]
> 従来の応答グループを移行する前に、Skype for Business Server 2019 プールで新しい Skype for Business Server 2019 応答グループを作成することができます。 
  
応答グループを従来のプールから Skype for Business Server 2019 に移行するには、 **Move-CsRgsConfiguration**コマンドレットを実行します。 
  
> [!IMPORTANT]
> 応答グループ移行コマンドレットは、プール全体の応答グループの構成を移動します。 特定のグループ、キュー、またはワークフローを選択して移行することはできません。 
  
応答グループを移行したら、Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルコマンドレットを使用して、すべてのエージェントグループ、キュー、およびワークフローが正常に移動されたことを確認する必要があります。 
  
応答グループを移行する場合、従来の応答グループは削除されません。 Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルのいずれかを使用して移行後に応答グループを管理すると、従来の応答グループと Skype for Business Server 2019 応答グループの両方を表示することができます。 更新プログラムは、Skype for Business Server 2019 応答グループにのみ適用する必要があります。 従来の応答グループは、ロールバックの目的でのみ保持されます。 
  
> [!CAUTION]
> 移行が完了し、新しい応答グループが作成されたら、Skype for Business Server コントロールパネルと Skype for Business Server 管理シェルによって、各応答グループのレガシおよび Skype for business Server 2019 のバージョンが表示されます。 従来の応答グループを削除するには、Skype for Business Server コントロールパネルまたは Skype for business Server 管理シェルを使用しないでください。 いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。 従来の応答グループは、従来のプールを使用停止にしたときに削除されます。 
  
> [!IMPORTANT]
> プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。 また、移行直後に応答グループをエクスポートすることを強くお勧めします。 従来の応答グループを削除する必要がある場合は、バックアップから応答グループを復元して、Skype for Business Server 2019 応答グループを再度実行することができます。 
  
Skype for Business Server 2019 には、**ワークフローの種類**と呼ばれる新しい応答グループ機能が導入されています。 [**ワークフローの種類**] は、[**管理**] または [**管理されていない**] に設定できます。 すべての応答グループは、[**ワークフローの種類**] が [**管理されていない**] に設定され、マネージャーの一覧が空の状態で移行されます。 
  
**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。 ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。 
  
応答グループ構成を移行するための次の手順では、従来のプールと Skype for Business Server 2019 プールとの間に1対1の関係があることを前提としています。 移行と展開時にプールを統合または分割する予定の場合は、どの従来のプールをどの Skype for Business Server 2019 プールにマッピングするかを計画する必要があります。
  
## <a name="to-migrate-response-group-configurations"></a>応答グループの構成を移行するには

1. RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
3. 実行
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    次に例を示します。
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 応答グループとエージェントを Skype for Business Server 2019 プールに移行すると、エージェントがサインインおよびサインアウトする際に使用する URL が Skype for Business Server 2019 の URL になり、[**ツール**] メニューから利用できるようになります。 ブックマークなどの参照を、新しい URL に更新するようにエージェントに知らせてください。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して応答グループの移行を確認するには

1. RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。 Skype for business Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [skype For Business server 2019 管理ツールを開く](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)」を参照してください。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 左側のナビゲーション ウィンドウで [**応答グループ**] をクリックします。
    
4. [**ワークフロー** ] タブで、従来の環境のすべてのワークフローがリストに含まれていることを確認します。 
    
5. [**キュー** ] タブをクリックし、従来の環境のすべてのキューがリストに含まれていることを確認します。 
    
6. [**グループ**] タブをクリックし、従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して応答グループの移行を確認するには

1. RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
    各コマンドレットの詳細については、次のように実行してください。
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 実行
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。
    
5. 実行
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 従来の環境のすべてのキューがリストに含まれていることを確認します。
    
7. 実行
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 従来の環境のすべてのワークフローがリストに含まれていることを確認します。
    

