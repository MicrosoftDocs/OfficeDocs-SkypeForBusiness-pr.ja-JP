---
title: 複数のユーザーをパイロット プールに移動します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 パイロット プールのビジネス サーバー 2019 のコントロール パネルまたは Skype の Skype を使用してビジネス サーバー 2019 管理シェルには、Skype を従来のプールから複数のユーザーを移動できます。
ms.openlocfilehash: c77598d531fa4640d64a61e22ace17e39d87b005
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233968"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>複数のユーザーをパイロット プールに移動します。

ビジネス サーバー 2019 パイロット プールのビジネス サーバー 2019 のコントロール パネルまたは Skype の Skype を使用してビジネス サーバー 2019 管理シェルには、Skype を従来のプールから複数のユーザーを移動できます。

 **この資料に記載されて**
  
[ビジネス サーバー 2019 のコントロール パネルの Skype を使用して複数のユーザーを移動するには](#sectionSection0)
  
[ビジネス サーバー 2019 管理シェルには、Skype を使用して複数のユーザーを移動するには](#sectionSection1)
  
[ビジネス サーバー 2019 管理シェルには、Skype を使用して同時にすべてのユーザーを移動するには](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>ビジネス サーバー 2019 のコントロール パネルの Skype を使用して複数のユーザーを移動するには
<a name="sectionSection0"> </a>

1. Skype をビジネス サーバーのコントロール パネルを開きます。
    
2. [**ユーザー**] をクリックして、**検索**] をクリックし、[**検索**] をクリックします。
    
3. Skype のビジネス サーバー 2019 プールに移動する 2 人のユーザーを選択します。 この例で、Chen 陽とクロースしました。 のユーザーを移動します。
    
     ![ユーザーを特定のレジスタのプールに移動します。](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. **[操作**] メニューから、**プールを選択したユーザーの移動**を選択します。
    
5. 」ドロップ ダウン リストから、Skype のビジネス サーバー 2019 プールを選択します。
    
6. [**アクション**] をクリックし、**プールを選択したユーザーの移動**] をクリックします。 **[OK]** をクリックします。
    
     ![ユーザーの移動先レジストラー プール] ダイアログ ボックス](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. ユーザーの**レジストラー プール**の列に今すぐビジネス サーバー 2019 のプールは、ユーザーが正常に移動されたことを示します、Skype が含まれていることを確認します。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>ビジネス サーバー 2019 管理シェルには、Skype を使用して複数のユーザーを移動するには
<a name="sectionSection1"> </a>

1. Skype をビジネス サーバー 2019 管理シェルを開きます。 
    
2. コマンド ・ ラインで、次の入力**User1**と**User2** 、移動する特定のユーザー名に置き換えるし、 **pool_FQDN**を移動先のプールの名前に置き換えます。 この例では、ユーザーが Hao Chen 教授のヨルダンを移動します。 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![CsUser の PowerShell Get コマンドレットの使用例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. コマンドラインで、次のように入力します。 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. **レジストラー プール**id は、前の手順では、 **pool_FQDN**として指定したプールにポイント必要がありますようになりました。 この id の存在は、ユーザーが正常に移動されたことを確認します。 **User2**が移動されたことを確認する手順を繰り返します。 
    
     ![出力の PowerShell Get ・ UsUser ・ アイデンティティのコマンドレット](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>ビジネス サーバー 2019 管理シェルには、Skype を使用して同時にすべてのユーザーを移動するには
<a name="sectionSection2"> </a>

この例では、すべてのユーザーを (pool01.contoso.net) の従来のプールに返されています。 ビジネス サーバー 2019 管理シェルには、Skype を使用して、私たちに移動されますすべてのユーザーを同時に、Skype のビジネス サーバー 2019 プール (pool02.contoso.net)。
  
1. Skype をビジネス サーバー 2019 管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell コマンドレットと管理シェルの結果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. パイロット ユーザーのいずれかの**Get CsUser**を実行します。 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. 各ユーザーの**レジストラー プール**id は、前の手順では、 **pool_FQDN**として指定したプールを指します。 この id の存在は、ユーザーが正常に移動されたことを確認します。 
    
5. 私たちことができます、Skype のビジネス サーバー 2019 のコントロール パネルのユーザーの一覧を表示また、レジストラー プールの値が、Skype のビジネス サーバー 2019 プールを指すことを確認します。
    
     ![Skype ビジネス サーバー 2019 コントロール パネルの [ユーザー] ボックスの一覧の](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

