---
title: Skype for Business Server でアーカイブを有効または無効にする
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '概要: Skype for Business Server でアーカイブを有効または無効にする方法について説明します。'
ms.openlocfilehash: 8c970dba9a76abdb0c9417a5da5c7aa642fa059c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818919"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Skype for Business Server でアーカイブを有効または無効にする

**概要:** Skype for Business Server でアーカイブを有効または無効にする方法について説明します。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブを有効または無効にする

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から適切なグローバル、サイト、またはプール構成を選択し、[**編集**] をクリックし、[**詳細の表示**] をクリックしてから次の操作を実行します。
    
   - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。
    
   - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
   - 構成のアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。
    
5. [**コミット**] をクリックします。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブを有効または無効にする

アーカイブは、**Set-CsArchivingConfiguration** コマンドレットを使用して有効または無効にすることもできます。 たとえば、次のコマンドは、IM セッションのみがアーカイブされるようにすべてのアーカイブ構成設定を変更します。 このコマンドは、**Get-CsArchivingConfiguration** コマンドレットをパラメーターなしで呼び出して、組織で現在使用されているすべてのアーカイブ構成設定を取得します。 次に、このコレクションは **Where-Object** コマンドレットにパイプ処理され、EnableArchiving プロパティが "ImAndWebConf" と等しい (-eq) 設定のみが選択されます。 そして、フィルターされたコレクションは **Set-CsArchivingConfiguration** コマンドレットにパイプ処理され、コレクション内の各項目が取得され、EnableArchiving の値が "ImOnly" に変更されます。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
