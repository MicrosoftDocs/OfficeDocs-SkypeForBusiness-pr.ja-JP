---
title: Skype for Business Server のエラーを処理するアーカイブオプションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '概要: Skype for Business Server に障害が発生したときに、アーカイブを防ぐことができる IM と会議セッションをブロックする方法について説明します。'
ms.openlocfilehash: 38f79277ff12aa8e716b034e8393a4d8b71cdbba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286240"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Skype for Business Server のエラーを処理するアーカイブオプションを構成する

**概要:** Skype for Business Server に障害が発生したときに、アーカイブを防ぐことができる IM と会議セッションをブロックする方法について説明します。
  
組織でアーカイブが必要な場合は、Skype for Business Server に障害が発生したときに、アーカイブを防ぐことができる IM と会議セッションをブロックすることができます。 この動作は重要モードと呼ばれることがあります。 たとえば、ストレージ サービスに問題が発生した場合、通信のアーカイブが有効になっているユーザーを対象に IM がブロックされます。 障害が解消されれば、IM も会議も自動的に復旧されます。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>コントロール パネルを使用して重要モードを構成する

アーカイブを阻む障害が発生した場合に通信セッションを許可するかどうかを指定するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。
    
5. 障害が発生したときのアーカイブの動作を設定するには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Windows PowerShell を使用して重要モードを構成する

また、BlockonCsArchivingConfiguration コマンドレットを使用して、アーカイブを禁止するエラーが発生した場合**** に通信セッションを許可するかどうかを指定することもできます。
  
たとえば、次のコマンドを実行すると、アーカイブに失敗した場合の通信が無効になります。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

次のコマンドは、アーカイブに障害が発生した場合でも通信を有効にします。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
  

