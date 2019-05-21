---
title: Skype for Business Server で既存のアーカイブポリシーを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '概要: Skype for Business Server のユーザーアーカイブポリシーを変更する方法について説明します。'
ms.openlocfilehash: 4a3da0bfe403d1a00807865cd07762111b59b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282022"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Skype for Business Server で既存のアーカイブポリシーを変更する
 
**概要:** Skype for Business Server のユーザーアーカイブポリシーを変更する方法について説明します。
  
初めて Skype for Business Server を展開するときは、展開のユーザーに対してアーカイブを実装する方法を決定する最初のアーカイブポリシーを設定します。 このトピックでは、ポリシーを管理および修正する方法について説明します。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを変更する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. ポリシー一覧で、次のいずれかを実行します。 
    
   - 展開全体のポリシーを変更するには、ポリシー一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
   - 単一のサイトのポリシーを変更するには、ポリシー一覧のサイト名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
   - 単一のユーザーまたはユーザー グループのポリシーを変更するには、ポリシー一覧のユーザー名またはユーザー グループ名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**アーカイブ ポリシーの編集**] ページで、次の操作を実行します。
    
   - ポリシーの内部アーカイブを有効または無効にするには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。
    
   - ポリシーの外部アーカイブを有効または無効にするには、[**外部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。
    
6. [**コミット**] をクリックします。
    
    > [!IMPORTANT]
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループにのみ適用されます。 詳細については、「 [Skype For Business Server でユーザーにアーカイブポリシーを適用する](apply-a-policy-to-users.md)」を参照してください。 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブ ポリシーを変更する

Windows PowerShell **Set-CsArchivingPolicy** コマンドレットを使用して、アーカイブ ポリシーを変更することもできます。
  
### <a name="enable-archiving-policies"></a>アーカイブ ポリシーを有効にする

内部通信セッションのアーカイブを有効にするには、 ArchiveInternal パラメーターの値を True ($True) に設定します。 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

外部通信セッションのアーカイブを有効にするには、ArchiveExternal パラメーターの値を True ($True) に設定します。 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

内部と外部の両方の通信セッションのアーカイブを有効にするには、アーカイブ内部パラメーターとアーカイブ外部パラメーターの両方の値を True に設定します。 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>アーカイブ ポリシーを無効にする

アーカイブを全体的に無効にするには、ArchiveInternal パラメーターと ArchiveExternal パラメーターの両方の値を False ($False) に設定します。 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
