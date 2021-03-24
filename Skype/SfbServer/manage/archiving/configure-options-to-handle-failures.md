---
title: Skype for Business Server の障害を処理するアーカイブ オプションを構成する
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '概要: アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM セッションと会議セッションをブロックする方法について説明します。'
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095451"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Skype for Business Server の障害を処理するアーカイブ オプションを構成する

**概要:** アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM セッションと会議セッションをブロックする方法について説明します。
  
アーカイブが組織の要件である場合は、アーカイブを妨げる Skype for Business Server 障害が発生した場合に IM セッションと会議セッションをブロックできます。 これは、クリティカル モードと呼ばれる場合があります。 たとえば、ストレージ サービスに問題がある場合、アーカイブ用に通信が有効になっているユーザーに対して IM がブロックされます。 障害から回復した後、IM および会議は自動的に回復します。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>コントロール パネルを使用してクリティカル モードを構成する

アーカイブを妨げる障害が発生した場合に通信セッションを許可するかどうかを指定するには、次のコマンドを実行します。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧で、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。
    
5. 障害が発生した場合のアーカイブの動作を設定するには、[アーカイブが失敗した場合にインスタント メッセージング **(IM)** セッションまたは Web 会議セッションをブロックする] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>アプリケーションを使用してクリティカル モードをWindows PowerShell

**また、BlockOnArchiveFailure パラメーターで Set-CsArchivingConfiguration** コマンドレットを使用して、アーカイブを妨げる障害が発生した場合に通信セッションを許可するかどうかを指定することもできます。
  
たとえば、次のコマンドは、アーカイブに失敗した場合の通信を無効にします。
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

次のコマンドは、アーカイブに失敗した場合の通信を有効にします。
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

詳細については [、Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
