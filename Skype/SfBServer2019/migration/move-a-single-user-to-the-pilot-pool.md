---
title: 1人のユーザーをパイロットプールに移動する
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
description: Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、ユーザーを従来のプールから Skype for Business Server 2019 パイロットプールに移動することができます。 次の例では、レジストラー pool 列で、pool01.contoso.net はレガシプールで、これらのユーザーの6人すべてがこのプールに接続されています。 Skype for business Server 2019 コントロールパネルと Skype for Business Server 管理シェルを使用してユーザーを Skype for business Server 2019 プールに移動するには、次の手順を使用します。
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752509"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>1人のユーザーをパイロットプールに移動する

Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 管理シェルを使用して、ユーザーを従来のプールから Skype for Business Server 2019 パイロットプールに移動することができます。 次の例では、**レジストラー pool**列で、 **pool01.contoso.net**はレガシプールで、これらのユーザーの6人すべてがこのプールに接続されています。 Skype for business Server 2019 コントロールパネルと Skype for Business Server 管理シェルを使用してユーザーを Skype for business Server 2019 プールに移動するには、次の手順を使用します。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Skype for Business Server 2019 コントロールパネルを使用してユーザーを移動するには
  
1. RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. **Skype For Business Server コントロールパネル**を開きます。
    
3. [**ユーザー**]、[**検索**]、[**ユーザー検索**] の順にクリックします。
    
4. Skype for Business Server 2019 プールに移動するユーザーを選択します。 この例では、Sara Davis というユーザーを移動します。
    
5. [**アクション**]メニューの [**選択されたユーザーをプールに移動**] をクリックします。
    
6. ドロップダウンリストから、[Skype for Business Server 2019] プールを選択します。
    
7. [**アクション**] をクリックし、[**選択されたユーザーをプールに移動**] をクリックします。 [**OK**] をクリックします。
  
8. ユーザーの [**レジストラー pool** ] 列に Skype For business Server 2019 プールが含まれるようになっていることを確認します。これは、ユーザーが正常に移動されたことを示します。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用してユーザーを移動するには

1. Skype for Business Server 管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool** identity は、Skype For business Server 2019 プールをポイントするようになりました。 この ID が存在していることにより、ユーザーが正常に移動されたことを確認できます。 

    > [!NOTE]
    > **Get-help user**コマンドレットの詳細については、次を実行してください。取得-**ヘルプ-Csuser-詳細**
  

