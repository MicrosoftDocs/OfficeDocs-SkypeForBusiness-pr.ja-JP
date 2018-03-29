---
title: Skype for Business Server 2015 でのアーカイブの有効化または無効化
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '概要: は、有効または、Skype のビジネス サーバー 2015 のアーカイブを無効にする方法を説明します。'
ms.openlocfilehash: ef4e24025d0f1c27b0249b4ea237a579882e74c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのアーカイブの有効化または無効化

**の概要:**有効にするか、Skype のビジネス サーバー 2015 のアーカイブを無効にする方法を説明します。
  
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

アーカイブは、**Set-CsArchivingConfiguration** コマンドレットを使用して有効または無効にすることもできます。 たとえば、次のコマンドは、IM セッションのみがアーカイブされるようにすべてのアーカイブ構成設定を変更します。 コマンドは、組織で使用して現在アーカイブのすべての構成設定を取得するためにパラメーターを指定せず**取得 CsArchivingConfiguration**コマンドレットを呼び出します。 このコレクションは**、コマンドレット、場所、EnableArchiving プロパティは設定のみを選択する**にはパイプ、(-eq)"ImAndWebConf"です。 **セット CsArchivingConfiguration**コマンドレットは、コレクション内の各項目を受け取るし、"ImOnly"に EnableArchiving の値を変更するには、フィルター処理されたコレクションはパイプは。
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```