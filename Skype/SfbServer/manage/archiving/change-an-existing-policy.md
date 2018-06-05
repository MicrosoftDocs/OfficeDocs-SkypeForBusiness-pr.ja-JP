---
title: Skype for Business Server 2015 での既存のアーカイブ ポリシーの変更
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '概要: は、ユーザーのポリシーを Skype のビジネス サーバー 2015 のアーカイブを変更する方法を説明します。'
ms.openlocfilehash: 21774eaff8b58c585b347e1f657aa7afcc3b6106
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569408"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での既存のアーカイブ ポリシーの変更
 
**の概要:** ユーザーのポリシーを Skype のビジネス サーバー 2015 のアーカイブを変更する方法について説明します。
  
ビジネス サーバー 2015 の Skype を最初に配置するときは、展開内のユーザーのアーカイブの実装方法を決定する初期のアーカイブ ・ ポリシーを設定します。 このトピックでは、ポリシーを管理および修正する方法について説明します。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ ポリシーを変更する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
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
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループにのみ適用されます。 詳細については、[ビジネス サーバー 2015 の Skype ユーザーにアーカイブ ・ ポリシーの適用](apply-a-policy-to-users.md)を参照してください。 
  
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

両方の内部および外部の通信セッションのアーカイブを有効にするには、ArchiveInternal と ArchiveExternal の両方のパラメーターの値を True に設定します。 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>アーカイブ ポリシーを無効にする

アーカイブを全体的に無効にするには、ArchiveInternal パラメーターと ArchiveExternal パラメーターの両方の値を False ($False) に設定します。 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```