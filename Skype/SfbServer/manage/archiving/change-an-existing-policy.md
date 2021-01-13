---
title: Skype for Business Server で既存のアーカイブ ポリシーを変更する
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '概要: Skype for Business Server のユーザー アーカイブ ポリシーを変更する方法について説明します。'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817707"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Skype for Business Server で既存のアーカイブ ポリシーを変更する
 
**概要:** Skype for Business Server のユーザー アーカイブ ポリシーを変更する方法について説明します。
  
最初に Skype for Business Server を展開するときに、展開内のユーザーに対してアーカイブを実装する方法を決定する初期アーカイブ ポリシーを設定します。 このトピックでは、ポリシーを管理および修正する方法について説明します。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを変更する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
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
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループのみに適用されます。 詳細については、「Skype for Business Server でアーカイブ ポリシーをユーザーに適用する [」を参照してください](apply-a-policy-to-users.md)。 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>アーカイブ ポリシーを使用してアーカイブ ポリシーをWindows PowerShell

**Set-CsArchivingPolicy** コマンドレットを使用してWindows PowerShellポリシーを変更することもできます。
  
### <a name="enable-archiving-policies"></a>アーカイブ ポリシーを有効にする

内部通信セッションのアーカイブを有効にするには、ArchiveInternal パラメーターの値を True ($True) に設定します。 
  
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
