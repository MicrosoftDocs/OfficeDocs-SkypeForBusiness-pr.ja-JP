---
title: サーバーのアーカイブ ポリシーを構成Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: '概要: このトピックでは、ユーザーの初期アーカイブ ポリシーを構成する方法Skype for Business Serverしてください。'
ms.openlocfilehash: 6e50f40aa91a26af8833ec7f330b14a9354d6b8b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399431"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>サーバーのアーカイブ ポリシーを構成Skype for Business Server
 
**概要:** このトピックでは、ユーザーの初期アーカイブ ポリシーを構成する方法Skype for Business Serverしてください。
  
このSkype for Business Serverポリシーを使用して、内部通信および外部通信のアーカイブを有効または無効にします。Skype for Business Server。 エクスポートできるものには、次のようなものがあります。
  
- 既定では、展開時に作成されるグローバル ポリシー Skype for Business Server
    
- 特定のサイトに対するアーカイブの実装方法を指定するオプションのサイト レベル のポリシー
    
- 特定のユーザーに対するアーカイブの実装方法を指定するオプションのユーザー レベル のポリシー
    
アーカイブを展開するときに最初にアーカイブ ポリシーを設定しましたが、展開後にポリシーを変更、追加、および削除できます。 [Skype for Business Server] コントロール パネルでは、[アーカイブと監視] グループの [アーカイブ ポリシー] ページを使用して、グローバル、サイト、およびユーザー レベルでポリシーを管理できます。
  
> [!NOTE]
> アーカイブの実装を制御するには、IM または会議のアーカイブ、クリティカル モードの使用、削除オプションなどのオプションを指定する必要があります。 既定では、グローバル アーカイブ構成またはサイトまたはプールのアーカイブ構成でオプションは有効になりません。 内部通信または外部通信のアーカイブを有効にする前に、すべての適切なオプションを指定する必要があります。 詳細については、「アーカイブ オプション[を構成する」を参照Skype for Business Server](configure-archiving-options.md)。 
  
> [!NOTE]
> 展開に対して Microsoft Exchange 統合を有効にした場合、Exchange In-Place Hold ポリシーは、Exchange に自宅にいてメールボックスを In-Place Hold に置くユーザーに対してアーカイブを有効にするかどうかを制御します。 
  
グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層など、アーカイブ ポリシーの動作の詳細については、「Plan [for archiving in Skype for Business Server」を参照してください](../../plan-your-deployment/archiving/archiving.md)。 展開後にポリシーを管理する方法の詳細については、「[Manage archiving policis in Skype for Business Server](../../manage/archiving/policies.md)。
  
## <a name="global-policy"></a>グローバル ポリシー

フロントエンド サーバーを展開すると、アーカイブSkype for Business Serverグローバル ポリシーが作成されます。 既定では、グローバル ポリシーではアーカイブは無効になっています。 グローバル ポリシーは、サイトポリシーまたはユーザー ポリシーを設定しない限り、展開全体の内部および外部通信に対してアーカイブを有効にするかどうかを制御します。グローバル ポリシーを上書きするか、または一部またはすべてのユーザーに Microsoft Exchange 統合を使用する場合。 Microsoft Exchange 統合を使用する場合、グローバル ポリシーは、Exchange に存在し、メールボックスを In-Place ホールドに置くユーザーには適用されません。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>アーカイブ データベースのアーカイブ用のグローバル ポリシー Skype for Business Server構成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. [**アーカイブ ポリシー**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] をクリックします。
    
5. [**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。
    
   - "グローバル" という既定の名前を使用しない場合は、[**名前**] にグローバル ポリシーの新しい名前を指定します。 
    
   - [ **説明**] で、ポリシーの内容に関する情報 (たとえば、divisionName のグローバル ポリシー)  *を指定します*  。
    
   - サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの内部通信のアーカイブを制御するには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。
    
   - サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
## <a name="site-policies"></a>サイト ポリシー

各サイトのアーカイブ ポリシーを作成することで、特定のサイトのアーカイブを有効または無効にできます。 サイト ポリシーはグローバル ポリシーより優先されますが、ユーザー ポリシーはサイト ポリシーを上書きします。 アーカイブ ポリシーは、Microsoft Exchange 統合を使用しない場合、または Microsoft Exchange 統合を使用していないが、Exchange にホームを持ち、メールボックスを In-Place 保留にしている一部のユーザーが含む場合にのみ適用されます。
  
### <a name="create-an-archiving-policy-for-a-site"></a>サイトのアーカイブ ポリシーを作成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
    グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層など、アーカイブ ポリシーの動作の詳細については、「Plan [for archiving in Skype for Business Server」を参照してください](../../plan-your-deployment/archiving/archiving.md)。
    
4. [**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。
    
5. [ **サイトの選択]** で、ポリシーを適用するサイトをクリックします。
    
6. **[新しいアーカイブ ポリシー]** で、次の操作を実行します。
    
   - [ **名前]** で、サイト ポリシーの名前を指定します。 
    
   - [ **説明**] で、サイト ポリシーの内容 (たとえば、Redmond のサイト ポリシー) に関する情報を提供します。
    
   - 指定したサイトの内部通信のアーカイブを制御するには、[内部通信をアーカイブする] チェック ボックス **をオンまたは** オフにします。
    
   - 指定したサイトの外部通信のアーカイブを制御するには、[外部通信をアーカイブする] チェック ボックス **を** オンまたはオフにします。
    
7. [**確定**] をクリックします。
    
## <a name="user-policies"></a>ユーザー ポリシー

特定のユーザーのアーカイブを有効または無効にするには、ユーザーのアーカイブ ポリシーを作成して構成し、そのポリシーを特定のユーザーまたはユーザー グループに適用します。 ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーより優先されます。 アーカイブ ポリシーは、Microsoft Exchange 統合を使用しない場合、または Microsoft Exchange 統合を使用していないが、Exchange にホームを持ち、メールボックスを In-Place 保留にしている一部のユーザーが含む場合にのみ適用されます。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>ユーザーに対してアーカイブ ポリシーを構成Skype for Business Server

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで、**[監視とアーカイブ]** をクリックし、**[アーカイブ ポリシー]** をクリックします。
    
4. **[新規]** をクリックし、**[ユーザー ポリシー]** をクリックします。
    
5. [**新しいアーカイブ ポリシー**] で、次の操作を実行します。
    
   - [**名前**] にユーザー ポリシーの名前を指定します。 
    
   - [**説明**] に、ユーザー ポリシーの内容に関する情報を入力します (「法務部門のユーザー ポリシー」など)。
    
   - ユーザー ポリシーの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
   - ユーザー ポリシーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
ユーザー ポリシーは、そのポリシーを割り当てたユーザーにのみ適用されます。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>ユーザーにSkype for Business Serverアーカイブ ポリシーを適用する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。
    
4. 検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**アーカイブ ポリシー Skype for Business Server** ユーザー **の編集] で**、適用するアーカイブ ユーザー ポリシーを選択します。
    
    > [!NOTE]
    > この設定 **\<Automatic\>** は、既定のサーバー インストール設定を適用します。 これらの設定はサーバーによって自動的に適用されます。
  
6. [**確定**] をクリックします。
    

