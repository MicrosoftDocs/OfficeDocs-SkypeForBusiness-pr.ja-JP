---
title: 既存のアーカイブ ポリシーを変更Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '概要: ユーザー のアーカイブ ポリシーを変更する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 494ed5ab3bd9e7bf4b64926533d3866e515fe34a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416620"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>既存のアーカイブ ポリシーを変更Skype for Business Server
 
**概要:** ユーザー のアーカイブ ポリシーを変更する方法について説明Skype for Business Server。
  
アプリケーションを最初に展開Skype for Business Server、展開内のユーザーに対するアーカイブの実装方法を決定する初期アーカイブ ポリシーを設定します。 このトピックでは、ポリシーを管理および修正する方法について説明します。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを変更する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. ポリシー一覧で、次のいずれかを実行します。 
    
   - 展開全体のポリシーを変更するには、ポリシー一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
   - 単一のサイトのポリシーを変更するには、ポリシー一覧のサイト名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
   - 単一のユーザーまたはユーザー グループのポリシーを変更するには、ポリシー一覧のユーザー名またはユーザー グループ名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**アーカイブ ポリシーの編集**]] ページで、次の操作を実行します。
    
   - ポリシーの内部アーカイブを有効または無効にするには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。
    
   - ポリシーの外部アーカイブを有効または無効にするには、[**外部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
    > [!IMPORTANT]
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループのみに適用されます。 詳細については、「[アーカイブ ポリシーをユーザーに](apply-a-policy-to-users.md)適用する」を参照Skype for Business Server。 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>アーカイブ ポリシーを使用してアーカイブ ポリシーをWindows PowerShell

また、**Set-CsArchivingPolicy** コマンドレットを使用Windows PowerShellアーカイブ ポリシーを変更することもできます。
  
### <a name="enable-archiving-policies"></a>アーカイブ ポリシーを有効にする

内部通信セッションのアーカイブを有効にするには、ArchiveInternal パラメーターの値を True ($True) に設定$True。 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

外部通信セッションのアーカイブを有効にするには、ArchiveExternal パラメーターの値を True ($True) に設定します。 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

内部通信セッションと外部通信セッションの両方のアーカイブを有効にするには、ArchiveInternal パラメーターと ArchiveExternal パラメーターの両方の値を True に設定します。 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>アーカイブ ポリシーを無効にする

アーカイブを完全に無効にするには、ArchiveInternal パラメーターと ArchiveExternal パラメーターの両方の値を False ($False) に設定します。 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
