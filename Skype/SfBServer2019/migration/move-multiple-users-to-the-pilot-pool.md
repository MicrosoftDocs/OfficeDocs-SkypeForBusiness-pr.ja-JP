---
title: 複数のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、従来のプールから Skype for business Server 2019 パイロットプールに複数のユーザーを移動することができます。
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753429"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>複数のユーザーをパイロットプールに移動する

Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、従来のプールから Skype for business Server 2019 パイロットプールに複数のユーザーを移動することができます。

 **この記事の内容**
  
[Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには](#sectionSection0)
  
[Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには](#sectionSection1)
  
[Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには
<a name="sectionSection0"> </a>

1. Skype for Business Server コントロールパネルを開きます。
    
2. [**ユーザー**]、[**検索**]、[**ユーザー検索**] の順にクリックします。
    
3. Skype for Business Server 2019 プールに移動する2人のユーザーを選択します。 この例では、Chen Yang および Claus Hansen というユーザーを移動します。
    
     ![ユーザーを特定の登録プールに移動する](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. [**アクション**] メニューで、[**選択されたユーザーをプールに移動**] をクリックします。
    
5. ドロップダウンリストから、[Skype for Business Server 2019] プールを選択します。
    
6. [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。 [**OK**] をクリックします。
    
     ![[ユーザーの移動]、[宛先レジストラープール] ダイアログボックス](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. ユーザーの [**レジストラープール**] 列に Skype For business Server 2019 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには
<a name="sectionSection1"> </a>

1. Skype for Business Server 2019 管理シェルを開きます。 
    
2. コマンドラインで、次のように入力し、 **User1**と**User2**を移動する特定のユーザー名に置き換えて、 **pool_FQDN**を移行先プールの名前に置き換えます。 この例では、ユーザーが Hao Chen と Katie ヨルダンを移動します。 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell の Get-CsUser コマンドレットの例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. **レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになります。 この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。 手順を繰り返して、 **User2**が移動されたことを確認します。 
    
     ![PowerShell の Get-UsUser-Identity コマンドレットの出力](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには
<a name="sectionSection2"> </a>

この例では、すべてのユーザーが従来のプール (pool01.contoso.net) に返されています。 Skype for Business Server 2019 管理シェルを使用して、すべてのユーザーを同時に Skype for Business Server 2019 プール (pool02.contoso.net) に移動します。
  
1. Skype for Business Server 2019 管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell コマンドレットと管理シェルの結果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. パイロットユーザーの1人に対して、 **Get-CsUser**を実行します。 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 各ユーザーの**レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになります。 この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。 
    
5. さらに、Skype for Business Server 2019 コントロールパネルでユーザーの一覧を表示し、レジストラープールの値が Skype for Business Server 2019 プールを指すようになっていることを確認できます。
    
     ![Skype for Business Server 2019 コントロールパネルのユーザーリスト](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

