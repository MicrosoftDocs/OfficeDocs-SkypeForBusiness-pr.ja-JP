---
title: Skype for Business Server でアーカイブ構成を作成する
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: '概要: Skype for Business Server のアーカイブ構成を作成する方法について説明します。'
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817657"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Skype for Business Server でアーカイブ構成を作成する

**概要:** Skype for Business Server のアーカイブ構成を作成する方法について説明します。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ オプションを構成する

特定のサイトまたはプールのアーカイブ オプションを構成するには: 
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. [**アーカイブ構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。 
    
   - サイト アーカイブ構成を作成するには、[サイトの構成] をクリックし、[サイトの選択] でアーカイブ用に構成するサイトを選択します。
    
   - プールアーカイブ構成を作成するには、[プールの構成] をクリックし、[プールの選択] でアーカイブ用に構成するプールを選択します。
    
5. [**新しいアーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リスト ボックスで、次のいずれかの操作を実行します。
    
   - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。
    
   - IM セッションと Web 会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
   - この構成のアーカイブを無効にするには、[アーカイブを無効にする **] をクリックします**。
    
6. [**新しいアーカイブ設定**] で、次の操作も実行します。
    
   - アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。
    
   - アーカイブ データをMicrosoft Exchange Serverするには **、[Microsoft Exchange** 統合] チェック ボックスをオンにします。
    
   - データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。
    
     - 一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。
    
     - エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。
    
7. [**確定**] をクリックします。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>アーカイブ オプションを構成するには、次のWindows PowerShell

**New-CsArchivingConfiguration** コマンドレットを使用して、特定のサイトまたはプールのアーカイブ オプションを構成することもできます。
  
次のコマンドを実行すると、レドモンドのサイト用に新しいアーカイブ構成設定のコレクションが作成されます。
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。 
  
異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。 次の例では、既定でインスタント メッセージング セッションのアーカイブのみを許可するアーカイブ構成設定のコレクションを作成します。
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

複数のパラメーターを含めることにより複数のプロパティ値を変更できます。たとえば、次のコマンドを実行すると、インスタント メッセージング セッションをアーカイブし、アーカイブ サービスのインスタント メッセージング サービスをブロックして使用不可にする新しい設定が構成されます。
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

詳細については [、New-CsArchivingConfiguration コマンドレットのヘルプ トピックを参照](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) してください。
