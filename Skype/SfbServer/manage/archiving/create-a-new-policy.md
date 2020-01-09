---
title: Skype for Business Server で新しいアーカイブポリシーを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '概要: Skype for Business Server 用の新しいアーカイブポリシーを作成する方法について説明します。'
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992734"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Skype for Business Server で新しいアーカイブポリシーを作成する

**概要:** Skype for Business Server 用の新しいアーカイブポリシーを作成する方法について説明します。
  
新しいアーカイブ ポリシーの作成には、コントロール パネルまたは Windows PowerShell コマンドレットを使用できます。
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>コントロール パネルを使用して新しいアーカイブ ポリシーを作成する

コントロール パネルを使用して新しいアーカイブ ポリシーを作成するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. [**新規**] をクリックし、次のいずれかの操作を実行します。 
    
   - サイトレベルのアーカイブ ポリシーを作成するには、[**サイト ポリシー**] をクリックし、[**サイトの選択**] で、ポリシーを適用するサイトをクリックします。
    
   - ユーザーレベルのアーカイブ ポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。
    
5. [**新しいアーカイブ ポリシー**] で、次の操作を実行します。
    
   - [**名前**] で、新しいポリシーの名前を指定します (externalContoso など)。
    
   - [**説明**] に、そのポリシーの内容に関する詳細を入力します (「Contoso の外部ユーザー アーカイブ ポリシー」など)。
    
   - 内部ユーザーとの通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
   - 外部ユーザーとの通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
    > [!IMPORTANT]
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループにのみ適用されます。 詳細については、「 [Skype For Business Server でユーザーにアーカイブポリシーを適用する](apply-a-policy-to-users.md)」を参照してください。 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Windows PowerShell を使用して新しいアーカイブ ポリシーを作成する

新しいアーカイブ ポリシーの作成には、Windows PowerShell の **New-CsArchivingPolicy** コマンドレットも使用できます。 詳細については、 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>サイト レベルでの新しいアーカイブ ポリシーを作成するには

次のコマンドは、Redmond サイトの新しいアーカイブ ポリシーを作成します。
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>ユーザーごとのレベルで新しいアーカイブ ポリシーを作成するには

ユーザーごとのレベルで新しいアーカイブ ポリシーを作成するには、ポリシーの作成時に一意の ID を指定します。
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>内部通信セッションのアーカイブを有効にする新しいアーカイブ ポリシーを作成するには

前の各コマンドでは (必須の ID パラメーター以外に) パラメーターが指定されていないため、新しいポリシーではすべてのプロパティで既定値が使用されます。 別のプロパティ値を使用するポリシーを作成するには、該当するパラメーターとパラメーター値を含めます。 たとえば、次のコマンドは、内部のインスタントメッセージングセッションのアーカイブを許可するアーカイブポリシーを作成します。 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>内部と外部の両通信セッションのアーカイブを有効にする新しいアーカイブ ポリシーを作成するには

複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、次のコマンドは、内部と外部の両方のインスタント メッセージング セッションをアーカイブするように新しいポリシーを構成します。
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
