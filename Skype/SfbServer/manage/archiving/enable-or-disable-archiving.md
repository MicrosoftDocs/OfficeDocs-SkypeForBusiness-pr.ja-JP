---
title: サーバーでアーカイブを有効または無効Skype for Business Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '概要: アーカイブを有効または無効にする方法については、Skype for Business Server。'
ms.openlocfilehash: c2aff3706505e8977080c92259f7d73a5c2b2b17
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839959"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>サーバーでアーカイブを有効または無効Skype for Business Server

**概要:** アーカイブを有効または無効にする方法については、Skype for Business Server。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブを有効または無効にする

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から適切なグローバル構成、サイト構成、またはプール構成を選択し、[編集]をクリックし、[詳細の表示] をクリックして、次の操作を実行します。
    
   - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、**[IM セッションのアーカイブ]** をクリックします。
    
   - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
   - 構成のアーカイブを無効にするには、[アーカイブを無効 **にする] をクリックします**。
    
5. [**確定**] をクリックします。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>アーカイブを使用してアーカイブを有効または無効Windows PowerShell

**Set-CsArchivingConfiguration** コマンドレットを使用して、アーカイブを有効または無効にすることもできます。 たとえば、次のコマンドは、IM セッションのみをアーカイブするアーカイブ構成設定を変更します。 このコマンドは **、Get-CsArchivingConfiguration** コマンドレットをパラメーターなしで呼び出して、組織内で現在使用されているアーカイブ構成設定を返します。 このコレクションは **Where-Object** コマンドレットにパイプ処理され、EnableArchiving プロパティが (-eq) "ImAndWebConf" と等しい設定のみを選択します。 フィルター処理されたコレクションは **Set-CsArchivingConfiguration** コマンドレットにパイプ処理され、コレクション内の各アイテムを受け取り、EnableArchiving の値を "ImOnly" に変更します。
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
