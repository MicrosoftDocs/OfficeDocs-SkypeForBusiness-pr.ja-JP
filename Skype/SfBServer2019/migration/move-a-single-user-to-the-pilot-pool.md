---
title: 1人のユーザーをパイロットプールに移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 Management Shell を使って、ユーザーを従来のプールから Skype for Business Server 2019 パイロットプールに移動することができます。 次の例では、レジストラー pool 列で、pool01.contoso.net はレガシプールであり、これらの6人のユーザーはこのプールに接続されています。 Skype for Business Server 2019 コントロールパネルと Skype for Business Server Management Shell を使って、ユーザーを Skype for business server 2019 プールに移動するには、次の手順を使用します。
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988962"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>1人のユーザーをパイロットプールに移動する

Skype for Business Server 2019 コントロールパネルまたは Skype for Business Server 2019 Management Shell を使って、ユーザーを従来のプールから Skype for Business Server 2019 パイロットプールに移動することができます。 次の例では、**レジストラー pool**列で、 **pool01.contoso.net**はレガシプールであり、これらの6人のユーザーはこのプールに接続されています。 Skype for Business Server 2019 コントロールパネルと Skype for Business Server Management Shell を使って、ユーザーを Skype for business server 2019 プールに移動するには、次の手順を使用します。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Skype for Business Server 2019 コントロールパネルを使用してユーザーを移動するには
  
1. RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. **Skype For Business Server コントロールパネル**を開きます。
    
3. [**ユーザー**] をクリックし、[**検索**] をクリックして、[**検索**] をクリックします。
    
4. Skype for Business Server 2019 プールに移動するユーザーを選択します。 この例では、Sara Davis というユーザーを移動します。
    
5. [**アクション**] メニューの [**選択されたユーザーをプールに移動**] をクリックします。
    
6. ドロップダウンリストから、Skype for Business Server 2019 プールを選択します。
    
7. [**操作**] をクリックし、[**選択したユーザーをプールに移動**] をクリックします。 **[OK]** をクリックします。
  
8. ユーザーの**レジストラー pool**列に Skype For business Server 2019 プールが含まれていることを確認します。これは、ユーザーが正常に移動されたことを示します。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Skype for Business Server 2019 管理シェルを使用してユーザーを移動するには

1. Skype for Business Server 管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 次に、コマンドラインで次のように入力します。 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool** id は、Skype For business Server 2019 プールをポイントするようになりました。 この id の存在は、ユーザーが正常に移動されたことを確認します。 

    > [!NOTE]
    > **ユーザーの取得**コマンドレットの詳細については、次を実行してください。 **Get-ヘルプ Get-Csuser-詳細**
  

