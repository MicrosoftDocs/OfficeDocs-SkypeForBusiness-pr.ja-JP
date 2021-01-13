---
title: Skype for Business Server で新しいアーカイブ ポリシーを作成する
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '概要: Skype for Business Server の新しいアーカイブ ポリシーを作成する方法について学習します。'
ms.openlocfilehash: 3e1f538aba26025f5868a09babd3b67df36f9a3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817647"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Skype for Business Server で新しいアーカイブ ポリシーを作成する

**概要:** Skype for Business Server の新しいアーカイブ ポリシーを作成する方法について学習します。
  
新しいアーカイブ ポリシーを作成するには、コントロール パネルを使用するか、次のコマンドレットWindows PowerShellします。
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>コントロール パネルを使用して新しいアーカイブ ポリシーを作成する

コントロール パネルを使用して新しいアーカイブ ポリシーを作成するには:
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. [**新規**] をクリックし、次のいずれかを実行します。 
    
   - サイト レベルのアーカイブ ポリシーを作成するには、[サイト ポリシー] をクリックし、[サイトの選択] でポリシーを適用するサイトをクリックします。
    
   - ユーザーレベルのアーカイブ ポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。
    
5. [**新しいアーカイブ ポリシー**] で、次の操作を実行します。
    
   - [**名前**] で、新しいポリシーの名前を指定します (externalContoso など)。
    
   - [**説明**] に、そのポリシーの内容に関する詳細を入力します (「Contoso の外部ユーザー アーカイブ ポリシー」など)。
    
   - 内部ユーザーとの通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
   - 外部ユーザーとの通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
    > [!IMPORTANT]
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループのみに適用されます。 詳細については、「Skype for Business Server でアーカイブ ポリシーをユーザーに適用する [」を参照してください](apply-a-policy-to-users.md)。 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>アーカイブ ポリシーを使用して新しいアーカイブ ポリシーをWindows PowerShell

**New-CsArchivingPolicy** コマンドレットを使用して、新Windows PowerShellアーカイブ ポリシーを作成することもできます。 詳細については [、New-CsArchivingPolicy コマンドレットのヘルプ トピックを参照](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) してください。
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>サイト レベルで新しいアーカイブ ポリシーを作成するには

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

前の各コマンドでは (必須の ID パラメーター以外に) パラメーターが指定されていないため、新しいポリシーではすべてのプロパティの既定値が使用されます。 別のプロパティ値を使用するポリシーを作成するには、該当するパラメーターとパラメーター値を含めます。 たとえば、次のコマンドは、内部インスタント メッセージング セッションのアーカイブを許可するアーカイブ ポリシーを作成します。 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>内部通信セッションと外部通信セッションの両方のアーカイブを有効にする新しいアーカイブ ポリシーを作成するには

複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。 たとえば、次のコマンドは、内部および外部の両方のインスタント メッセージング セッションをアーカイブする新しいポリシーを構成します。
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
