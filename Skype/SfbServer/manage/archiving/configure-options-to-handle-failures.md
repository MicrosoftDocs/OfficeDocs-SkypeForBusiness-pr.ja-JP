---
title: アーカイブ オプションを構成して、エラーを処理Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '概要: アーカイブを妨げる障害が発生した場合に IM セッションと会議セッションSkype for Business Serverする方法について説明します。'
ms.openlocfilehash: f3f20bf53a784972c720ce5578d78462cbb222c8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836469"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>アーカイブ オプションを構成して、エラーを処理Skype for Business Server

**概要:** アーカイブを妨げる障害が発生した場合に IM および会議セッションSkype for Business Serverする方法について説明します。
  
アーカイブが組織の要件である場合は、アーカイブを妨げる可能性がある障害が発生した場合に IM Skype for Business Server会議セッションをブロックできます。 これは、クリティカル モードと呼ばれる場合があります。 たとえば、ストレージ サービスに問題がある場合、アーカイブ用に通信が有効になっているユーザーに対して IM がブロックされます。 障害から回復した後、IM および会議は自動的に回復します。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>コントロール パネルを使用してクリティカル モードを構成する

アーカイブを妨げる障害が発生した場合に通信セッションを許可するかどうかを指定するには、次のコマンドを実行します。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
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
