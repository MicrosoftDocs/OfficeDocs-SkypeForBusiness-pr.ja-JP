---
title: Skype for Business Server でダイヤルイン会議の PIN ポリシーを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '概要: Skype for Business Server でダイヤルイン会議の PIN ポリシーを管理する方法について説明します。'
ms.openlocfilehash: 567d57edc4db5bae87653d8d3e11e44054efc0cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818478"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン会議の PIN ポリシーを管理する
 
**概要:** Skype for Business Server でダイヤルイン会議の PIN ポリシーを管理する方法について説明します。
  
組織内の Active Directory ドメインサービス (AD DS) の資格情報を持っている Skype for Business Server ユーザーは、暗証番号 (PIN) を使って、認証されたユーザーとしてダイヤルイン会議に参加できます。 PIN ポリシーは、ダイヤルイン会議 PIN がどのように機能するかについてのルールを定義します。
  
 組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用でき、必要に応じて変更することもできます。グローバル PIN ポリシーは、ダイヤルイン会議 PIN のルールを、フォレスト レベルで定義します。グローバル PIN ポリシーを変更することはできますが、削除することはできません。
  
特定のポリシーをサイトまたは特定のユーザー グループに適用する場合は、新しい PIN ポリシーを作成できます。
  
PIN ポリシーは、最も狭いスコープから最も広いスコープまでのどのスコープでも、ユーザーに適用されます。 ユーザーレベルの PIN ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。 ユーザー ポリシーを割り当てない場合は、サイトレベルの PIN ポリシーがあれば、そのポリシーが適用されます。 ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル PIN ポリシーが既定の設定を提供します。
  
## <a name="view-information-about-pin-policies"></a>PIN ポリシーに関する情報を表示する

PIN ポリシーに関する情報を表示するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、PIN ポリシーに関する情報を表示する

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー**] ページで、表示する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して PIN ポリシーに関する情報を表示する

PIN ポリシーに関する情報を表示するには、**Get-CsPinPolicy** コマンドレットを使用します。 たとえば、次のコマンドを実行すると、site:Redmond という Identity を持つ 1 つの PIN ポリシーに関する情報が返されます。
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

詳細については、「 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)」を参照してください。
  
## <a name="modify-the-global-pin-policy"></a>グローバル PIN ポリシーを変更する

グローバル PIN ポリシーを変更するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、グローバルなダイヤルイン会議 PIN ポリシーを変更する

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー**] ページで、[**グローバル**] ポリシー、[**編集**]、[**詳細の表示**] の順にクリックします。
    
5. [**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。既定の最小サイズは 5 桁です。
    
6. ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。
    
7. [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。
    
8. PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。
    
9. [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。
    
10. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。
    
11. PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。
    
    > [!IMPORTANT]
    > セキュリティ上の理由により、共通のパターンは許可しないことをお勧めします。 
  
12. [**コミット**] をクリックします。
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ダイヤルイン会議 PIN のグローバルポリシーを変更する

グローバル ダイヤルイン会議 PIN ポリシーを変更するには、**Set-CsPinPolicy** コマンドレットを使用します。
  
次のコマンドは、組織内で使用するよう構成されているすべての PIN ポリシーの MinPasswordLength の値を変更します。これを行うため、まずパラメーターを何も指定しない **Get-CsPinPolicy** コマンドレットを呼び出して、すべての既存の PIN ポリシーのコレクションを取得しています。次に、そのコレクションを **Set-CsPinPolicy** コマンドレットにパイプ処理し、コレクション内の各ポリシーの MinPasswordLength プロパティの値を変更しています。
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

詳細については、「 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)」を参照してください。
  
## <a name="create-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを作成する

ユーザーまたはサイトの PIN ポリシーを作成するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ユーザーまたはサイトの PIN ポリシーを作成する

1. RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー**] ページで [**新規**] をクリックして、次のいずれかを実行します。
    
   - ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。[**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。
    
   - サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。サイトの一覧で、対象のサイトをクリックして [**OK**] をクリックします。
    
5. [**説明**] フィールドに、PIN ポリシーの説明を入力します。
    
6. [**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。既定の最小サイズは 5 桁です。
    
7. ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。
    
8. [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。
    
9. PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。
    
10. [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。
    
11. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。
    
12. PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。
    
    > [!IMPORTANT]
    > セキュリティ上の理由により、共通のパターンは許可しないことをお勧めします。 
  
13. [**コミット**] をクリックします。
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してユーザーまたはサイトの PIN ポリシーを作成する

ユーザーまたはサイトの PIN ポリシーを作成するには、**New-CsPinPolicy** コマンドレットを使用します。
  
次のコマンドでは、site:Redmond という Identity を持つ新しい PIN ポリシーを作成します。このコマンドには、ただ 1 つのオプションのパラメーターである MinPasswordLength が含まれています。このパラメーターを使用して、MinPasswordLength プロパティを 7 に設定します。ポリシーの残りすべてのプロパティは、既定値を使用して構成されます。
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 詳細については、「 [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)」を参照してください。
  
## <a name="modify-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを変更する

ユーザーまたはサイトの PIN ポリシーを変更するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ユーザーまたはサイトの PIN ポリシーを変更する

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー**] ページで、変更する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**PIN ポリシーの編集**] で、ポリシー名以外のポリシー設定を変更します。ポリシー名は変更できません。
    
6. [**確定**] をクリックします。
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを変更する

ダイヤルイン会議 PIN ポリシーを変更するには、**Set-CsPinPolicy** コマンドレットを使用します。
  
次のコマンドでは、Redmond サイトに割り当てた PIN ポリシーを変更しています。この例では、MinPasswordLength プロパティの値を 10 に変更しています。これは、新しい PIN を 10 桁以上にしなければならないことを意味します。
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

詳細については、「 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)」を参照してください。
  
## <a name="delete-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを削除する

ユーザーまたはサイトの PIN ポリシーを削除するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ユーザーまたはサイトの PIN ポリシーを削除する

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー**] ページで、変更する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**削除**] をクリックします。
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ユーザーまたはサイトの PIN ポリシーを削除する

ユーザーまたはサイトの PIN ポリシーを削除するには、**Remove-CsPinPolicy** コマンドレットを使用します。
  
次のコマンドは、サイト スコープで構成されていたすべての PIN ポリシーを削除します。これを実行するには、まず Filter パラメーターを指定して **Get-CsPinPolicy** コマンドレットを使用し、Identity が文字列 "site:" で始まるすべてのポリシーのコレクションを戻します。次に、このコレクションは **Remove-CsPinPolicy** コマンドレットにパイプ処理され、コレクション内の各ポリシーが削除されます。
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

詳細については、「 [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)」を参照してください。
  

