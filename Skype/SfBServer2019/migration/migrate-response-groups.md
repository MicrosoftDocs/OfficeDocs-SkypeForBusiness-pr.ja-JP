---
title: 応答グループの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイル、および、従来の展開から Skype for Business Server 2019 プールへの応答グループの連絡先オブジェクトの移動が含まれます。 従来の応答グループを移行すると、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールでは処理されなくなりました。
ms.openlocfilehash: cba50526748ca15c04513013e484b0e279410c1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298205"
---
# <a name="migrate-response-groups"></a>応答グループの移行

ユーザーが Skype for Business Server 2019 プールに移動された後、応答グループを移行できます。 応答グループの移行には、エージェントグループ、キュー、ワークフロー、オーディオファイル、および、従来の展開から Skype for Business Server 2019 プールへの応答グループの連絡先オブジェクトの移動が含まれます。 従来の応答グループを移行すると、応答グループへの通話は、Skype for Business Server 2019 プールの応答グループアプリケーションによって処理されます。 応答グループへの通話は、従来のプールでは処理されなくなりました。
  
> [!NOTE]
> すべてのユーザーを Skype for Business Server 2019 プールに移動する前に、応答グループを移行することはできますが、すべてのユーザーを最初に移動することをお勧めします。 特に、応答グループのエージェントであるユーザーは、Skype for Business Server 2019 プールに移動するまで、新機能のすべての機能を利用できません。 
  
応答グループを移行する前に、応答グループアプリケーションが含まれている Skype for Business Server 2019 プールを展開しておく必要があります。 応答グループアプリケーションは、エンタープライズボイスの展開時に既定でインストールされ、有効になります。 **ApplicationServer**コマンドレットを実行して、応答グループアプリケーションがインストールされていることを確認できます。 
  
> [!NOTE]
> 従来の応答グループを移行する前に、Skype for business Server 2019 プールで新しい Skype for Business Server 2019 応答グループを作成することができます。 
  
従来のプールから Skype for Business Server 2019 に応答グループを移行するには、 **Move-CsRgsConfiguration**コマンドレットを実行します。 
  
> [!IMPORTANT]
> 応答グループの移行コマンドレットは、プール全体の応答グループの構成を移動します。 移行する特定のグループ、キュー、またはワークフローを選ぶことはできません。 
  
応答グループを移行した後、Skype for Business Server コントロールパネルまたは Skype for Business Server Management Shell コマンドレットを使用して、すべてのエージェントグループ、キュー、ワークフローが正常に移動されたことを確認する必要があります。 
  
応答グループを移行しても、従来の応答グループは削除されません。 Skype for Business Server コントロールパネルまたは Skype for Business Server Management Shell を使用して、移行後に応答グループを管理すると、従来の応答グループと Skype for Business Server 2019 応答グループの両方を表示できます。 更新プログラムは、Skype for Business Server 2019 応答グループにのみ適用する必要があります。 従来の応答グループは、ロールバック目的でのみ保持されます。 
  
> [!CAUTION]
> 移行が完了し、新しい応答グループが作成された後、Skype for Business Server コントロールパネルと Skype for business server の管理シェルでは、各回答のレガシおよび Skype for business Server 2019 バージョンが表示されます。化. Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使って、従来の応答グループを削除しないでください。 いずれかを削除すると、移行中に作成された対応する応答グループは動作を停止します。 従来の応答グループは、レガシープールの使用を停止すると削除されます。 
  
> [!IMPORTANT]
> プールを廃止するまでは、前の展開からデータを削除しないことをお勧めします。 また、移行した後すぐに応答グループをエクスポートすることを強くお勧めします。 従来の応答グループを削除する必要がある場合は、バックアップから応答グループを復元して、Skype for Business Server 2019 応答グループをもう一度実行することができます。 
  
Skype for Business Server 2019 では、**ワークフローの種類**と呼ばれる新しい返信グループ機能が導入されています。 **ワークフローの種類**は、**管理**または**非**管理を行うことができます。 すべての応答グループは、**ワークフローの種類**が [**非管理**] に設定され、[管理者] リストが空の状態で移行されます。 
  
**移動-CsRgsConfiguration**コマンドレットを実行しても、ロールバックのために、エージェントグループ、キュー、ワークフロー、オーディオファイルは従来のプールに残ります。 ただし、従来のプールにロールバックする必要がある場合は、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを従来のプールに戻す必要があります。 
  
回答グループの構成を移行するための次の手順では、従来のプールと Skype for Business Server 2019 プールの間に1対1のリレーションシップがあることを前提としています。 移行および展開中にプールを統合または分割する場合は、どのレガシプールが Skype for Business Server 2019 プールにマップされるかを計画する必要があります。
  
## <a name="to-migrate-response-group-configurations"></a>応答グループの構成を移行するには

1. RTCUniversalServerAdmins グループのメンバーであるアカウントか、同等の管理者権限と権限を持つアカウントでコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
3. 次のコマンドレットを実行します。
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    次に例を示します。
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 応答グループとエージェントを Skype for Business Server 2019 プールに移行した後、サインインとサインアウトのためにエージェントで使用される URL は、Skype for Business Server 2019 URL であり、[**ツール**] メニューから使用できます。 ブックマークなどの参照を新しい URL に更新するようにエージェントに通知します。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して応答グループの移行を確認するには

1. RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 Skype for business Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [skype For Business server 2019 管理ツールを開く](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)」をご覧ください。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 左側のナビゲーションウィンドウで、[**応答グループ**] をクリックします。
    
4. [**ワークフロー** ] タブで、従来の環境のすべてのワークフローが一覧に含まれていることを確認します。 
    
5. [**キュー** ] タブをクリックして、従来の環境のすべてのキューがリストに含まれていることを確認します。 
    
6. [**グループ**] タブをクリックして、従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して応答グループの移行を確認するには

1. RTCUniversalReadOnlyAdmins group のメンバーであるアカウント、または CsViewOnlyAdministrator の役割のメンバーであるアカウントでコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
    次のコマンドレットの詳細については、次を実行します。
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. 次のコマンドレットを実行します。
    
   ```
   Get-CsRgsAgentGroup
   ```

4. 従来の環境のすべてのエージェントグループがリストに含まれていることを確認します。
    
5. 次のコマンドレットを実行します。
    
   ```
   Get-CsRgsQueue
   ```

6. 従来の環境のすべてのキューがリストに含まれていることを確認します。
    
7. 次のコマンドレットを実行します。
    
   ```
   Get-CsRgsWorkflow
   ```

8. 従来の環境のすべてのワークフローがリストに含まれていることを確認します。
    

