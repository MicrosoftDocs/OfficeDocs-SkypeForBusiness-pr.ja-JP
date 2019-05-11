---
title: ビジネス サーバーの Skype での障害を処理するためにアーカイブのオプションを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '概要: アーカイブを妨げるビジネス サーバー障害の IM と会議のセッションの場合は、Skype をブロックする方法を説明します。'
ms.openlocfilehash: 356db70f9e1be630b8ff6daa8b619b13caf817b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885046"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>ビジネス サーバーの Skype での障害を処理するためにアーカイブのオプションを構成します。

**の概要:** アーカイブを妨げるビジネス サーバー障害の IM と会議のセッションの場合は、Skype をブロックする方法を説明します。
  
アーカイブは、組織の必要な場合、Skype のアーカイブを妨げるビジネス サーバー障害の発生時に IM および会議セッションをブロックできます。 この動作は重要モードと呼ばれることがあります。 たとえば、ストレージ サービスに問題が発生した場合、通信のアーカイブが有効になっているユーザーを対象に IM がブロックされます。 障害が解消されれば、IM も会議も自動的に復旧されます。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>コントロール パネルを使用して重要モードを構成する

アーカイブを阻む障害が発生した場合に通信セッションを許可するかどうかを指定するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。
    
5. 障害が発生したときのアーカイブの動作を設定するには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Windows PowerShell を使用して重要モードを構成する

BlockOnArchiveFailure パラメーターを使用して**セット CsArchivingConfiguration**コマンドレットを使用してアーカイブを妨げる障害が発生した場合の通信セッションを許可するかどうかを指定することもできます。
  
たとえば、次のコマンドは、アーカイブが失敗した場合の通信を無効にします。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

次のコマンドは、アーカイブに障害が発生した場合でも通信を有効にします。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

詳細については、[セット CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

