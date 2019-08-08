---
title: 複数のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 Management Shell を使用して、従来のプールから Skype for Business Server 2019 パイロットプールに複数のユーザーを移動することができます。
ms.openlocfilehash: 6c6f61287cfc75b7500317d62de4ea846af1abd3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244573"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>複数のユーザーをパイロットプールに移動する

Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 Management Shell を使用して、従来のプールから Skype for Business Server 2019 パイロットプールに複数のユーザーを移動することができます。

 **この記事の内容**
  
[Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには](#sectionSection0)
  
[Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには](#sectionSection1)
  
[Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Skype for Business Server 2019 コントロールパネルを使用して複数のユーザーを移動するには
<a name="sectionSection0"> </a>

1. Skype for Business Server コントロールパネルを開きます。
    
2. [**ユーザー**] をクリックし、[**検索**] をクリックして、[**検索**] をクリックします。
    
3. Skype for Business Server 2019 プールに移動する2人のユーザーを選びます。 この例では、Chen Yang sold と Claus というユーザーを移動します。
    
     ![ユーザーを特定のレジスタプールに移動する](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. [**アクション**] メニューで、[**選択したユーザーをプールに移動**] を選択します。
    
5. ドロップダウンリストから、Skype for Business Server 2019 プールを選択します。
    
6. [**操作**] をクリックし、[**選択したユーザーをプールに移動**] をクリックします。 **[OK]** をクリックします。
    
     ![[ユーザーの移動]、[宛先レジストラー pool] ダイアログボックス](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. ユーザーの**レジストラー pool**列に Skype For business Server 2019 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用して複数のユーザーを移動するには
<a name="sectionSection1"> </a>

1. Skype for Business Server 2019 管理シェルを開きます。 
    
2. コマンドラインで、次のように入力し、移動する特定のユーザー名で**User1**と**User2**を置き換えて、 **pool_FQDN**を目的のプールの名前に置き換えます。 この例では、ユーザーの Hao Chen と Katie ヨルダンを移動します。 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-CsUser コマンドレットの例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. コマンドラインで、次のように入力します。 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. **レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになります。 この id の存在は、ユーザーが正常に移動されたことを確認します。 手順を繰り返して、 **User2**が移動されたことを確認します。 
    
     ![PowerShell Get-UsUser Identity コマンドレットの出力](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用してすべてのユーザーを同時に移動するには
<a name="sectionSection2"> </a>

この例では、すべてのユーザーが従来のプール (pool01.contoso.net) に戻されています。 Skype for Business Server 2019 管理シェルを使用して、すべてのユーザーを Skype for Business Server 2019 プール (pool02.contoso.net) に同時に移行します。
  
1. Skype for Business Server 2019 管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell コマンドレットと結果の管理シェル](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. パイロットユーザーのいずれかに対して **、ユーザーの購入ユーザー**を実行します。 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. 各ユーザーの**レジストラープール**id は、前の手順で**pool_FQDN**として指定したプールを指すようになりました。 この id の存在は、ユーザーが正常に移動されたことを確認します。 
    
5. さらに、Skype for Business Server 2019 コントロールパネルでユーザーの一覧を表示し、[レジストラー Pool] の値が Skype for Business Server 2019 プールを指すようになったことを確認します。
    
     ![Skype for Business Server 2019 コントロールパネルのユーザーリスト](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

