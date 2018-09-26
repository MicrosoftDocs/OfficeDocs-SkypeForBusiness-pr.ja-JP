---
title: 1 人のユーザーをパイロット プールに移動します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 パイロット プールのビジネス サーバー 2019 のコントロール パネルまたは Skype の Skype を使用してビジネス サーバー 2019 管理シェルには、Skype を従来のプールからユーザーを移動できます。 レジストラー プール] 列に、次の例で pool01.contoso.net は、従来のプールでは、および 6 のこれらのユーザーがこのプールに接続しています。 ビジネス サーバー 2019 プールのサーバー管理シェルのビジネスのビジネス サーバー 2019 のコントロール パネルと Skype の Skype を使用して、Skype にユーザーを移動するのにには、次の手順を使用します。
ms.openlocfilehash: f04cccf29fd88bf1da95f4d67f6e47c51b878717
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028811"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>1 人のユーザーをパイロット プールに移動します。

ビジネス サーバー 2019 パイロット プールのビジネス サーバー 2019 のコントロール パネルまたは Skype の Skype を使用してビジネス サーバー 2019 管理シェルには、Skype を従来のプールからユーザーを移動できます。 **レジストラー プール**] 列に、次の例で**pool01.contoso.net**は、従来のプールでは、および 6 のこれらのユーザーがこのプールに接続しています。 ビジネス サーバー 2019 プールのサーバー管理シェルのビジネスのビジネス サーバー 2019 のコントロール パネルと Skype の Skype を使用して、Skype にユーザーを移動するのにには、次の手順を使用します。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>ビジネス サーバー 2019 のコントロール パネルの Skype を使用してユーザーを移動するには
  
1. RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。
    
2. **Skype ビジネス サーバーのコントロール パネル**を開きます。
    
3. [**ユーザー**] をクリックして、**検索**] をクリックし、[**検索**] をクリックします。
    
4. Skype のビジネス サーバー 2019 プールに移動するユーザーを選択します。 この例では、佐々木さんの岡崎のユーザーを移動します。
    
5. [**アクション**] メニューの [**選択されたユーザーをプールに移動**] をクリックします。
    
6. 」ドロップ ダウン リストから、Skype のビジネス サーバー 2019 プールを選択します。
    
7. [**アクション**] をクリックし、**プールを選択したユーザーの移動**] をクリックします。 [**OK**] をクリックします。
  
8. **レジストラー プール**] 列ユーザーにはに今すぐビジネス サーバー 2019 のプールは、ユーザーが正常に移動されたことを示します、Skype が含まれていることを確認します。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>ビジネス サーバー 2019 管理シェルには、Skype を使用してユーザーを移動するには

1. Skype をビジネス サーバー管理シェルを開きます。
    
2. コマンドラインで、次のように入力します。 
    
  ```
  Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
  ```

3. 次に、コマンド ・ ラインでは、次のように入力します。 
    
  ```
  Get-CsUser -Identity "David Pelton"
  ```

4. **RegistrarPool** id は、ビジネス サーバー 2019 プールの Skype を指します。 この id の存在は、ユーザーが正常に移動されたことを確認します。 

    > [!NOTE]
    > **Get CsUser**コマンドレットの詳細についてを実行: **Get-csuser からのヘルプを表示-詳細な**
  

