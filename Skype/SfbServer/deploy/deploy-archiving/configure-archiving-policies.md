---
title: Skype for Business Server のアーカイブ ポリシーを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: '概要: このトピックでは、Skype for Business Server ユーザーの初期アーカイブ ポリシーを構成する方法について説明します。'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820857"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Skype for Business Server のアーカイブ ポリシーを構成する
 
**概要:** このトピックでは、Skype for Business Server ユーザーの初期アーカイブ ポリシーを構成する方法について説明します。
  
Skype for Business Server では、ポリシーを使用して、Skype for Business Server にホームを持つユーザーの内部通信および外部通信のアーカイブを有効または無効にします。 エクスポートできるものには、次のようなものがあります。
  
- Skype for Business Server を展開するときに既定で作成されるグローバル ポリシー
    
- 特定のサイトに対してアーカイブを実装する方法を指定するオプションのサイト レベルポリシー
    
- 特定のユーザーに対してアーカイブを実装する方法を指定するオプションのユーザー レベルのポリシー
    
アーカイブ ポリシーは、アーカイブの展開時に最初に設定しますが、展開後にポリシーを変更、追加、および削除できます。 Skype for Business Server コントロール パネルでは、アーカイブおよび監視グループの[アーカイブ ポリシー] ページを使用して、グローバル レベル、サイト レベル、およびユーザー レベルのポリシーを管理できます。
  
> [!NOTE]
> アーカイブの実装を制御するには、IM または会議をアーカイブするかどうか、重要モードの使用、削除オプションなどのオプションを指定する必要があります。 既定では、グローバル アーカイブ構成またはサイトまたはプールのアーカイブ構成では、どのオプションも有効になりません。 内部通信または外部通信のアーカイブを有効にする前に、すべての適切なオプションを指定する必要があります。 詳細については [、「Skype for Business Server のアーカイブ オプションを構成する」を参照してください](configure-archiving-options.md)。 
  
> [!NOTE]
> 展開に対して Microsoft Exchange 統合を有効にした場合、Exchange In-Place 保持ポリシーは、Exchange にホームを置き、メールボックスが In-Place Hold に設定されているユーザーに対してアーカイブを有効にするかどうかを制御します。 
  
グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層など、アーカイブ ポリシーがどのように機能するのかについては [、「Plan for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)を参照してください。 展開後にポリシーを管理する方法の詳細については、「Skype for Business Server でアーカイブ ポリシーを管理 [する」を参照してください](../../manage/archiving/policies.md)。
  
## <a name="global-policy"></a>グローバル ポリシー

フロントエンド サーバーを展開すると、Skype for Business Server はアーカイブ用のグローバル ポリシーを作成します。 既定では、グローバル ポリシーではアーカイブは無効になっています。 グローバル ポリシーは、グローバル ポリシーを上書きするサイト ポリシーまたはユーザー ポリシーを設定しない限り、または一部またはすべてのユーザーに Microsoft Exchange 統合を使用しない限り、展開全体で内部通信と外部通信に対してアーカイブを有効にするかどうかを制御します。 Microsoft Exchange 統合を使用する場合、グローバル ポリシーは、Exchange にホームとして設定され、メールボックスが In-Place保持に設定されているユーザーには適用されません。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Skype for Business Server アーカイブ データベースのアーカイブ用のグローバル ポリシーを構成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
4. [**アーカイブ ポリシー**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] をクリックします。
    
5. [**アーカイブ ポリシーの編集 - グローバル**] で、以下の手順を実行します。
    
   - "グローバル" という既定の名前を使用しない場合は、[**名前**] にグローバル ポリシーの新しい名前を指定します。 
    
   - [ **説明]** に、ポリシーの内容に関する情報 (例: divisionName のグローバル ポリシー  *) を指定します*  。
    
   - サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの内部通信のアーカイブを制御するには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。
    
   - サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトとユーザーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
## <a name="site-policies"></a>サイト ポリシー

特定のサイトのアーカイブを有効または無効にするには、各サイトのアーカイブ ポリシーを作成します。 サイト ポリシーはグローバル ポリシーより優先されますが、ユーザー ポリシーはサイト ポリシーより優先されます。 アーカイブ ポリシーは、Microsoft Exchange 統合を使用しない場合、または Microsoft Exchange 統合を使用しているが、Exchange にホームではなく、メールボックスが In-Place Hold に設定されている一部のユーザーが含む場合にのみ適用されます。
  
### <a name="create-an-archiving-policy-for-a-site"></a>サイトのアーカイブ ポリシーを作成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。
    
    グローバル ポリシー、サイト ポリシー、ユーザー ポリシーの階層など、アーカイブ ポリシーがどのように機能するのかについては [、「Plan for archiving in Skype for Business Server」](../../plan-your-deployment/archiving/archiving.md)を参照してください。
    
4. [**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。
    
5. [ **サイトの選択]** で、ポリシーを適用するサイトをクリックします。
    
6. **[新しいアーカイブ ポリシー]** で、次の操作を実行します。
    
   - [ **名前]** で、サイト ポリシーの名前を指定します。 
    
   - [ **説明]** に、サイト ポリシーの内容に関する情報 (たとえば、Redmond のサイト ポリシー) を入力します。
    
   - 指定したサイトの内部通信のアーカイブを制御するには、[内部通信のアーカイブ] **チェック ボックスを** オンまたはオフにします。
    
   - 指定したサイトの外部通信のアーカイブを制御するには、[外部通信をアーカイブする] **チェック ボックスを** オンまたはオフにします。
    
7. [**確定**] をクリックします。
    
## <a name="user-policies"></a>ユーザー ポリシー

ユーザーのアーカイブ ポリシーを作成および構成し、そのポリシーを特定のユーザーまたはユーザー グループに適用することで、特定のユーザーのアーカイブを有効または無効にできます。 ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーより優先されます。 アーカイブ ポリシーは、Microsoft Exchange 統合を使用しない場合、または Microsoft Exchange 統合を使用しているが、Exchange にホームではなく、メールボックスが In-Place Hold に設定されている一部のユーザーが含む場合にのみ適用されます。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Skype for Business Server にホームのユーザーのアーカイブ ポリシーを構成する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで、**[監視とアーカイブ]** をクリックし、**[アーカイブ ポリシー]** をクリックします。
    
4. **[新規]** をクリックし、**[ユーザー ポリシー]** をクリックします。
    
5. [**新しいアーカイブ ポリシー**] で、次の操作を実行します。
    
   - [**名前**] にユーザー ポリシーの名前を指定します。 
    
   - [**説明**] に、ユーザー ポリシーの内容に関する情報を入力します (「法務部門のユーザー ポリシー」など)。
    
   - ユーザー ポリシーの内部通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
   - ユーザー ポリシーの外部通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。
    
6. [**確定**] をクリックします。
    
ユーザー ポリシーは、そのポリシーを割り当てたユーザーにのみ適用されます。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>ユーザーに Skype for Business Server アーカイブ ポリシーを適用する

1. CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。
    
4. 検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**アーカイブ ポリシー] の [Skype for Business Server** ユーザーの編集] で、適用するアーカイブ ユーザー ポリシーを選択します。
    
    > [!NOTE]
    > この **\<Automatic\>** 設定では、既定のサーバー インストール設定が適用されます。 これらの設定はサーバーによって自動的に適用されます。
  
6. [**確定**] をクリックします。
    

