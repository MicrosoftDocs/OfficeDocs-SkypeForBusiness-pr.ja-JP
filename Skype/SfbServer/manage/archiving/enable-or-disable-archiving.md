---
title: Skype for Business Server でアーカイブを有効または無効にする
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '概要: Skype for Business Server でアーカイブを有効または無効にする方法について学習します。'
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817597"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Skype for Business Server でアーカイブを有効または無効にする

**概要:** Skype for Business Server でアーカイブを有効または無効にする方法について学習します。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブを有効または無効にする

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から適切なグローバル構成、サイト構成、またはプール構成を選択し、[編集]をクリックし、[詳細の表示] をクリックして、次の操作を行います。
    
   - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、**[IM セッションのアーカイブ]** をクリックします。
    
   - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
   - 構成のアーカイブを無効にするには、[アーカイブを無効にする **] をクリックします**。
    
5. [**確定**] をクリックします。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>アーカイブを有効または無効にするには、次のWindows PowerShell

**Set-CsArchivingConfiguration** コマンドレットを使用して、アーカイブを有効または無効にすることもできます。 たとえば、次のコマンドは、すべてのアーカイブ構成設定を変更して、IM セッションのみをアーカイブします。 このコマンドは、パラメーターを指定せずに **Get-CsArchivingConfiguration** コマンドレットを呼び出して、組織で現在使用されているアーカイブ構成設定を戻します。 次に、このコレクションを **Where-Object** コマンドレットにパイプ処理し、EnableArchiving プロパティが "ImAndWebConf" と等しい (-eq) 設定のみを選択します。 次に、フィルター処理されたコレクションを **Set-CsArchivingConfiguration** コマンドレットにパイプ処理し、コレクション内の各項目を取得し、EnableArchiving の値を "ImOnly" に変更します。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
