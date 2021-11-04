---
title: 新しいアーカイブ ポリシーを作成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '概要: 新しいアーカイブ ポリシーを作成する方法についてSkype for Business Server。'
ms.openlocfilehash: a07edaae5d8c7c7cafc0e9a76d2b2d7574c5713b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767895"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>新しいアーカイブ ポリシーを作成Skype for Business Server

**概要:** 新しいアーカイブ ポリシーを作成する方法についてSkype for Business Server。
  
新しいアーカイブ ポリシーは、コントロール パネルを使用するか、新しいコマンドレットを使用Windows PowerShellできます。
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>コントロール パネルを使用して新しいアーカイブ ポリシーを作成する

コントロール パネルを使用して新しいアーカイブ ポリシーを作成するには、次の操作を行います。
  
1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。 
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
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
    > ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループのみに適用されます。 詳細については、「[アーカイブ ポリシーをユーザーに](apply-a-policy-to-users.md)適用する」を参照Skype for Business Server。 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>アーカイブ ポリシーを使用して新しいアーカイブ ポリシーをWindows PowerShell

**New-CsArchivingPolicy** コマンドレットを使用して、新Windows PowerShellアーカイブ ポリシーを作成することもできます。 詳細については [、New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>サイト レベルで新しいアーカイブ ポリシーを作成するには

次のコマンドは、Redmond サイトの新しいアーカイブ ポリシーを作成します。
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>ユーザー単位で新しいアーカイブ ポリシーを作成するには

ユーザー単位で新しいアーカイブ ポリシーを作成するには、ポリシーの作成時に一意の ID を指定します。
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>内部通信セッションのアーカイブを有効にする新しいアーカイブ ポリシーを作成するには

前の各コマンドでは (必須の ID パラメーター以外に) パラメーターが指定されていないため、新しいポリシーではすべてのプロパティの既定値が使用されます。 別のプロパティ値を使用するポリシーを作成するには、該当するパラメーターとパラメーター値を含めます。 たとえば、次のコマンドは、内部インスタント メッセージング セッションのアーカイブを許可するアーカイブ ポリシーを作成します。 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>内部通信セッションと外部通信セッションの両方をアーカイブできる新しいアーカイブ ポリシーを作成するには

複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。 たとえば、次のコマンドは、内部および外部の両方のインスタント メッセージング セッションをアーカイブする新しいポリシーを構成します。
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```