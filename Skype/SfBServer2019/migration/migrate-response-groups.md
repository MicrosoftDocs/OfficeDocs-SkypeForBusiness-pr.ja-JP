---
title: 応答グループの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ユーザーが 2019 年 2019 Skype for Business Serverに移動された後、応答グループを移行できます。 応答グループの移行には、エージェント グループ、キュー、ワークフロー、オーディオ ファイルのコピー、およびレガシ展開から Skype for Business Server 2019 プールへの応答グループの連絡先オブジェクトの移動が含まれます。 従来の応答グループを移行すると、応答グループへの呼び出しは、2019 プール内の応答グループ Skype for Business Server処理されます。 応答グループへの呼び出しは、レガシ プールによって処理されなくなりました。
ms.openlocfilehash: 96eecb0ad10a900a9d00d26383e149ceec4cbfe8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588029"
---
# <a name="migrate-response-groups"></a>応答グループの移行

ユーザーが 2019 年 2019 Skype for Business Serverに移動された後、応答グループを移行できます。 応答グループの移行には、エージェント グループ、キュー、ワークフロー、オーディオ ファイルのコピー、およびレガシ展開から Skype for Business Server 2019 プールへの応答グループの連絡先オブジェクトの移動が含まれます。 従来の応答グループを移行すると、応答グループへの呼び出しは、2019 プール内の応答グループ Skype for Business Server処理されます。 応答グループへの呼び出しは、レガシ プールによって処理されなくなりました。
  
> [!NOTE]
> すべてのユーザーを 2019 年 2019 年のプールに移動する前にSkype for Business Serverグループを移行することもできますが、最初にすべてのユーザーを移動することをお勧めします。 特に、応答グループ エージェントであるユーザーは、2019 プールに移動するまで、新機能の完全な機能Skype for Business Serverされません。 
  
応答グループを移行する前に、応答グループ アプリケーションをSkype for Business Server 2019 プールを展開している必要があります。 応答グループ アプリケーションは、既定でインストールおよびアクティブ化されます。このアプリケーションを展開エンタープライズ VoIP。 **Get-CsService -ApplicationServer** コマンドレットを実行して、応答グループ アプリケーションがインストールされていることを確認できます。 
  
> [!NOTE]
> 従来の応答グループSkype for Business Server移行する前に、Skype for Business Server 2019 プールに新しい 2019 応答グループを作成できます。 
  
応答グループを従来のプールから 2019 Skype for Business Serverに移行するには **、Move-CsRgsConfiguration コマンドレットを実行** します。 
  
> [!IMPORTANT]
> 応答グループ移行コマンドレットは、プール全体の応答グループ構成を移動します。 特定のグループ、キュー、またはワークフローを選択して移行することはできません。 
  
応答グループを移行した後、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルコマンドレットを使用して、すべてのエージェント グループ、キュー、およびワークフローが正常に移動されたことを確認する必要があります。 
  
応答グループを移行すると、従来の応答グループは削除されません。 Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して移行後に応答グループを管理すると、従来の応答グループと Skype for Business Server 2019 応答グループの両方を確認できます。 更新プログラムは、2019 年Skype for Business Serverにのみ適用する必要があります。 従来の応答グループはロールバックの目的でのみ保持されます。 
  
> [!CAUTION]
> 移行が完了し、新しい応答グループが作成されると、Skype for Business Server コントロール パネルと Skype for Business Server 管理シェルに、各応答グループの従来バージョンと Skype for Business Server 2019 バージョンが表示されます。 従来の応答グループSkype for Business Server削除Skype for Business Serverコントロール パネルまたは管理シェルを使用しない。 削除すると、移行中に作成された対応する応答グループが動作を停止します。 レガシ プールを使用停止すると、レガシ応答グループは削除されます。 
  
> [!IMPORTANT]
> プールの使用を停止するまで、以前の展開からデータを削除しないようにすることをお勧めします。 また、移行直後に応答グループをエクスポートすることを強くお勧めします。 従来の応答グループを削除する必要がある場合は、バックアップから応答グループを復元して、2019 Skype for Business Serverを再度実行できます。 
  
Skype for Business Server 2019 では、ワークフローの種類と呼ばれる新しい応答グループ **機能が導入されています**。 [**ワークフローの種類**] は、[**管理**] または [**管理されていない**] に設定できます。 すべての応答グループは、[**ワークフローの種類**] が [**管理されていない**] に設定され、マネージャーの一覧が空の状態で移行されます。 
  
**Move-CsRgsConfiguration** コマンドレットを実行した場合、エージェント グループ、キュー、ワークフロー、およびオーディオ ファイルは、ロールバックできるようにレガシ プールに残されたままとなります。ただし、レガシ プールへのロールバックが必要な場合に連絡先オブジェクトを移動してレガシ プールに戻すには、**Move-CsApplicationEndpoint** コマンドレットを実行する必要があります。 
  
応答グループ構成を移行する次の手順では、従来のプールと 2019 年の 2019 年のプールの間に 1 対 1 のSkype for Business Server前提とします。 移行および展開中にプールを統合または分割する予定の場合は、2019 プールにマップする従来のプールを計画Skype for Business Server必要があります。
  
## <a name="to-migrate-response-group-configurations"></a>応答グループ構成を移行するには

1. RTCUniversalServerAdmins グループのメンバーであるアカウント、またはそれと同等の管理者権限およびアクセス許可を持つアカウントを使用して、コンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [スタート] をクリックし、[すべてのプログラム] をクリックし、[Microsoft Skype for Business Server **2019]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. 次を実行します: 
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    次に例を示します。
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 応答グループとエージェントを Skype for Business Server 2019 プールに移行した後、エージェントがサインインおよびサインアウトに使用する URL は Skype for Business Server 2019 URL であり、[ツール] メニューから **使用** できます。 ブックマークなどの参照を、新しい URL に更新するようにエージェントに知らせてください。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して応答グループの移行Skype for Business Server確認するには

1. RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 コントロール パネルの起動に使用できるさまざまな方法のSkype for Business Serverについては[、「Open Skype for Business Server 2019](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)管理ツール」を参照してください。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 左側のナビゲーション ウィンドウで [**応答グループ**] をクリックします。
    
4. [ワークフロー **] タブ** で、従来の環境のすべてのワークフローがリストに含まれているか確認します。 
    
5. [キュー **] タブを** クリックし、従来の環境内のすべてのキューがリストに含まれているか確認します。 
    
6. [グループ **] タブ** をクリックし、従来の環境内のすべてのエージェント グループがリストに含まれているか確認します。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して応答グループSkype for Business Server確認するには

1. RTCUniversalReadOnlyAdmins グループのメンバーまたは少なくとも CsViewOnlyAdministrator 役割のメンバーであるアカウントを使用して、コンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [スタート] をクリックし、[すべてのプログラム] をクリックし、[Microsoft Skype for Business Server **2019]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
    各コマンドレットの詳細については、次のように実行してください。
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 次を実行します: 
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 従来の環境内のすべてのエージェント グループがリストに含まれているか確認します。
    
5. 次を実行します: 
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 従来の環境内のすべてのキューが一覧に含まれているか確認します。
    
7. 次を実行します: 
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 従来の環境内のすべてのワークフローがリストに含まれているか確認します。
