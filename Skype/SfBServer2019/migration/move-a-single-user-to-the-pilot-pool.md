---
title: 1 人のユーザーをパイロット プールに移動する
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
description: Skype for Business Server 2019 コントロール パネルまたは Skype for Business Server 管理シェルを使用して、従来のプールから Skype for Business Server 2019 パイロット プールにユーザーを移動できます。 次の例では、[レジストラー プール] 列で、pool01.contoso.net がレガシ プールであり、これらの 6 人のユーザーすべてがこのプールに接続されています。 Skype for Business Server 2019 コントロール パネルと管理シェルを使用して、Skype for Business Server 2019 プールにユーザーを移動するには、次Skype for Business Serverします。
ms.openlocfilehash: 98fd1ce168cf5b44a85c1b0a93ee90634a84f885ced3cb3ffaaca8cee836a620
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303391"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>1 人のユーザーをパイロット プールに移動する

Skype for Business Server 2019 コントロール パネルまたは Skype for Business Server 管理シェルを使用して、従来のプールから Skype for Business Server 2019 パイロット プールにユーザーを移動できます。 次の例では、[**レジスト** ラー プール] 列で、pool01.contoso.net がレガシ プールであり、これらの 6 人のユーザーすべてがこのプールに接続されています。 Skype for Business Server 2019 コントロール パネルと管理シェルを使用して、Skype for Business Server 2019 プールにユーザーを移動するには、次Skype for Business Serverします。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>2019 コントロール パネルを使用してユーザー Skype for Business Server移動するには
  
1. RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. [**コントロール Skype for Business Server] を開きます**。
    
3. [**ユーザー**]、[**検索**]、[**ユーザー検索**] の順にクリックします。
    
4. 2019 プールに移動するユーザー Skype for Business Server選択します。 この例では、Sara Davis というユーザーを移動します。
    
5. [**アクション**]メニューの [**選択されたユーザーをプールに移動**] をクリックします。
    
6. ドロップダウン リストから、2019 年Skype for Business Server選択します。
    
7. [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。[**OK**] をクリックします。
  
8. ユーザーの **レジストラー プール列** に、ユーザーが正常に移動されたことをSkype for Business Server 2019 プールが含まれているかどうかを確認します。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>2019 管理シェルを使用してユーザー Skype for Business Server移動するには

1. 管理シェルSkype for Business Server開きます。
    
2. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool** ID は、2019 年Skype for Business Serverをポイントします。 この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。 

    > [!NOTE]
    > **Get-CsUser コマンドレット** の詳細については **、「Get-Help Get-CsUser -Detailed」を実行します。**
  

