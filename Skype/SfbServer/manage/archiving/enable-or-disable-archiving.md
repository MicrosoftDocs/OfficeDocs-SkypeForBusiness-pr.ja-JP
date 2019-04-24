---
title: 有効にするか、Skype のビジネス サーバーのアーカイブを無効にします。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '概要: は、有効または、Skype のビジネス サーバーのアーカイブを無効にする方法を説明します。'
ms.openlocfilehash: b7f9ab424a9fc24c733fa61c75c1d4564b636941
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250911"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>有効にするか、Skype のビジネス サーバーのアーカイブを無効にします。

**の概要:** 有効にするか、Skype のビジネス サーバーのアーカイブを無効にする方法を説明します。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブを有効または無効にする

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. アーカイブ構成の一覧から適切なグローバル、サイト、またはプール構成を選択し、[**編集**] をクリックし、[**詳細の表示**] をクリックしてから次の操作を実行します。
    
   - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。
    
   - IM セッションと会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
   - 構成のアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。
    
5. [**コミット**] をクリックします。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブを有効または無効にする

アーカイブは、**Set-CsArchivingConfiguration** コマンドレットを使用して有効または無効にすることもできます。 たとえば、次のコマンドは、IM セッションのみがアーカイブされるようにすべてのアーカイブ構成設定を変更します。 このコマンドは、**Get-CsArchivingConfiguration** コマンドレットをパラメーターなしで呼び出して、組織で現在使用されているすべてのアーカイブ構成設定を取得します。 次に、このコレクションは **Where-Object** コマンドレットにパイプ処理され、EnableArchiving プロパティが "ImAndWebConf" と等しい (-eq) 設定のみが選択されます。 そして、フィルターされたコレクションは **Set-CsArchivingConfiguration** コマンドレットにパイプ処理され、コレクション内の各項目が取得され、EnableArchiving の値が "ImOnly" に変更されます。
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
