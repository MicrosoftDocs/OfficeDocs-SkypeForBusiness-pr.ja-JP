---
title: ビジネス サーバーの Skype では、アーカイブの構成を作成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 概要では、Skype のビジネス サーバーのアーカイブ構成を作成する方法について説明します。
ms.openlocfilehash: 2a45a627ab8bbeedd18d1cbda636606ebc641745
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881285"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>ビジネス サーバーの Skype では、アーカイブの構成を作成します。

**の概要:** Skype のビジネス サーバーのアーカイブ構成を作成する方法について説明します。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>コントロール パネルを使用してアーカイブ オプションを構成する

特定のサイトまたはプールのアーカイブ オプションを構成するには 
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。
    
4. [**アーカイブ構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。 
    
   - サイトのアーカイブ構成を作成するには、[**サイト構成**] をクリックし、[**サイトの選択**] で、アーカイブ用に構成するサイトを選択します。
    
   - プールのアーカイブ構成を作成するには、[**プール構成**] をクリックし、[**プールの選択**] で、アーカイブ用に構成するプールを選択します。
    
5. [**新しいアーカイブ設定**] の [**アーカイブ設定**] ドロップダウン リスト ボックスで、次のいずれかの操作を実行します。
    
   - インスタント メッセージング (IM) セッションのアーカイブだけを有効にするには、[**IM セッションをアーカイブする**] をクリックします。
    
   - IM セッションと Web 会議の両方のアーカイブを有効にするには、[**IM および Web 会議セッションをアーカイブする**] をクリックします。
    
   - この構成のアーカイブを無効にするには、[**アーカイブを無効にする**] をクリックします。
    
6. [**新しいアーカイブ設定**] で、次の操作も実行します。
    
   - アーカイブを使用できない場合にアクティビティをブロックするには、[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**] チェック ボックスをオンにします。
    
   - アーカイブ ・ データを格納する Microsoft Exchange Server を使用するには、 **Microsoft Exchange の統合**] チェック ボックスをクリックします。
    
   - データの削除を有効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のどちらかの操作を実行します。
    
     - 一定の日数が経過した後に削除されるよう指定するには、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。
    
     - エクスポートされたアーカイブ データに削除対象を限定するには、[**エクスポートされたアーカイブ データのみを削除する**] をクリックします。
    
7. [**確定**] をクリックします。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Windows PowerShell を使用してアーカイブ オプションを構成する

**New-CsArchivingConfiguration** コマンドレットを使用して、特定のサイトまたはプールのアーカイブ オプションを構成することもできます。
  
次のコマンドを実行すると、レドモンドのサイト用に新しいアーカイブ構成設定のコレクションが作成されます。
  
```
New-CsArchivingConfiguration -Identity "site:Redmond"
```

このコマンドでは (必須の Identity パラメーター以外の) パラメーターが指定されていないため、新しい構成設定のコレクションでは、すべてのプロパティに既定値が使用されます。 
  
異なるプロパティ値を使用する設定を作成するには、該当するパラメーターとパラメーター値を追加します。次の例では、既定ではインスタント メッセージング セッションのアーカイブのみを許可するアーカイブ構成設定のコレクションを作成します。
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

複数のパラメーターを含めることにより複数のプロパティ値を変更できます。たとえば、次のコマンドを実行すると、インスタント メッセージング セッションをアーカイブし、アーカイブ サービスのインスタント メッセージング サービスをブロックして使用不可にする新しい設定が構成されます。
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

詳細については、[新規 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
