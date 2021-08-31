---
title: 複数のユーザーをパイロット プールに移動する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server 2019 コントロール パネルまたは Skype for Business Server 2019 管理シェルを使用して、レガシ プールから Skype for Business Server 2019 パイロット プールに複数のユーザーを移動できます。
ms.openlocfilehash: fc4d14d26a76ff4dbfc690fc7517aba77afd253f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726316"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>複数のユーザーをパイロット プールに移動する

Skype for Business Server 2019 コントロール パネルまたは Skype for Business Server 2019 管理シェルを使用して、レガシ プールから Skype for Business Server 2019 パイロット プールに複数のユーザーを移動できます。

 **この記事の内容**
  
[2019 コントロール パネルを使用して複数Skype for Business Server移動するには](#sectionSection0)
  
[2019 管理シェルを使用してSkype for Business Serverを移動するには](#sectionSection1)
  
[2019 管理シェルを使用してすべてのユーザー Skype for Business Server移動するには](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>2019 コントロール パネルを使用して複数Skype for Business Server移動するには
<a name="sectionSection0"> </a>

1. [コントロール Skype for Business Server] を開きます。
    
2. [**ユーザー**]、[**検索**]、[**ユーザー検索**] の順にクリックします。
    
3. 2019 プールに移動する 2 人Skype for Business Server選択します。 この例では、Chen Yang および Claus Hansen というユーザーを移動します。
    
     ![ユーザーを特定の登録プールに移動します。](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. [**アクション**] メニューで、[**選択されたユーザーをプールに移動**] をクリックします。
    
5. ドロップダウン リストから、2019 年Skype for Business Server選択します。
    
6. [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。[**OK**] をクリックします。
    
     ![[ユーザーの移動] ダイアログ ボックスの [移行先レジストラー プール] ダイアログ ボックス。](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. ユーザーの **レジストラー プール列** に、ユーザーが正常に移動されたことをSkype for Business Server 2019 プールが含まれているかどうかを確認します。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>2019 管理シェルを使用してSkype for Business Serverを移動するには
<a name="sectionSection1"> </a>

1. 2019 Skype for Business Serverシェルを開きます。 
    
2. コマンド ラインで、次のコマンドを入力し **、User1** と **User2** を移動する特定のユーザー名に置き換え、pool_FQDN を移動先プール **の名前** に置き換します。 この例では、ユーザー Hao Chen と Katie Jordan を移動します。 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell のコマンドレットGet-CsUserします。](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. レジスト **ラー プール ID** は、前の手順で指定した **プールpool_FQDNポイント** する必要があります。 この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。 手順を繰り返して **、User2 が移動** されたことを確認します。 
    
     ![-Identity コマンドレットGet-UsUser PowerShell の出力。](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>2019 管理シェルを使用してすべてのユーザー Skype for Business Server移動するには
<a name="sectionSection2"> </a>

この例では、すべてのユーザーが従来のプール (pool01.contoso.net) に戻されています。 2019 Skype for Business Server管理シェルを使用して、すべてのユーザーを同時に Skype for Business Server 2019 プール (pool02.contoso.net) に移動します。
  
1. 2019 Skype for Business Serverシェルを開きます。
    
2. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell コマンドレットと管理シェルの結果。](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. パイロット **ユーザーの 1 人に対して Get-CsUser** を実行します。 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 各 **ユーザーのレジスト** ラー プール ID は、前の手順で指定した **pool_FQDNをポイント** します。 この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。 
    
5. さらに、Skype for Business Server 2019 コントロール パネルでユーザーの一覧を表示し、レジストラー プールの値が Skype for Business Server 2019 プールをポイントSkype for Business Serverできます。
    
     ![Skype for Business Server 2019 コントロール パネルのユーザー リスト。](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

