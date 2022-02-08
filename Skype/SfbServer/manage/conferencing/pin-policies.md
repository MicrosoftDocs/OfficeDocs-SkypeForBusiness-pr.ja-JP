---
title: ダイヤルイン会議の PIN ポリシーを管理する (Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '概要: ダイヤルイン会議の PIN ポリシーを管理する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 93ee04292ec3ea06299b91c75c2c2fe89a2b2298
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385609"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>ダイヤルイン会議の PIN ポリシーを管理する (Skype for Business Server
 
**概要:** ダイヤルイン会議の PIN ポリシーを管理する方法については、Skype for Business Server。
  
Skype for Business Server Active Directory ドメイン サービス (AD DS) 資格情報を持つユーザーは、個人識別番号 (PIN) を使用して、認証されたユーザーとしてダイヤルイン会議に参加できます。 PIN ポリシーは、ダイヤルイン会議 PIN の動作に関するルールを定義します。
  
 組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用し、必要に応じて変更できます。 グローバル PIN ポリシーは、ダイヤルイン会議 PIN のルールを、フォレスト レベルで定義します。 グローバル PIN ポリシーは変更できますが、削除することはできません。
  
特定のポリシーをサイトまたは特定のユーザー グループに適用する場合は、新しい PIN ポリシーを作成できます。
  
PIN ポリシーは、最も狭い範囲から最も広い範囲のユーザーに適用されます。 ユーザー レベルの PIN ポリシーをユーザーに割り当てる場合、これらの設定が優先されます。 ユーザー ポリシーを割り当てない場合は、サイト レベルの PIN ポリシーが適用されます (存在する場合)。 ユーザーポリシーまたはサイト ポリシーが適用されない場合、グローバル PIN ポリシーは既定の設定を提供します。
  
## <a name="view-information-about-pin-policies"></a>PIN ポリシーに関する情報を表示する

PIN ポリシーに関する情報を表示するには、コントロール パネルSkype for Business Server管理シェルを使用Skype for Business Server使用します。
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して PIN ポリシーに関するSkype for Business Server表示する

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー] ページで**、表示する PIN ポリシーをクリックし、[編集] をクリックし、[詳細の表示] **をクリックします**。
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して PIN ポリシーに関するSkype for Business Server表示する

PIN ポリシーに関する情報を表示するには、 **Get-CsPinPolicy コマンドレットを使用** します。 たとえば、次のコマンドは、Identity サイト:Redmond を持つ 1 つの PIN ポリシーに関する情報を返します。
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

完全な構文の説明とパラメーターの一覧を含む詳細については、「 [Get-CsPinPolicy」を参照してください](/powershell/module/skype/get-cspinpolicy?view=skype-ps)。
  
## <a name="modify-the-global-pin-policy"></a>グローバル PIN ポリシーの変更

グローバル PIN ポリシーは、コントロール パネルまたは管理シェルSkype for Business Server使用して変更Skype for Business Serverできます。
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用してグローバルダイヤルイン会議 PIN ポリシー Skype for Business Serverする

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページで、[**グローバル**] ポリシー、[**編集**]、[**詳細の表示**] の順にクリックします。
    
5. [**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。 既定の最小サイズは 5 桁です。
    
6. ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。
    
7. [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。
    
8. PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。
    
9. [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。
    
10. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。
    
11. PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。
    
    > [!IMPORTANT]
    > セキュリティ上の理由から、一般的なパターンを許可しない方法をお勧めします。 
  
12. [**確定**] をクリックします。
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用してグローバルダイヤルイン会議 PIN Skype for Business Server変更する

グローバル ダイヤルイン会議 PIN ポリシーを変更するには、 **Set-CsPinPolicy コマンドレットを使用** します。
  
次のコマンドは、組織内で使用するように構成されているすべての PIN ポリシーの MinPasswordLength の値を変更します。 これを行うには、すべての既存の PIN ポリシーのコレクションを取得するために、パラメーターを指定せずに **Get-CsPinPolicy** コマンドレットを最初に呼び出します。 そのコレクションは **Set-CsPinPolicy** コマンドレットにパイプ処理され、コレクション内の各ポリシーの MinPasswordLength プロパティの値を変更します。
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

完全な構文の説明とパラメーターの一覧を含む詳細については、「 [Set-CsPinPolicy」を参照してください](/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="create-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを作成する

ユーザーまたはサイトの PIN ポリシーを作成するには、コントロール パネルSkype for Business Server管理シェルを使用Skype for Business Server使用します。
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用してユーザーまたはサイトの PIN Skype for Business Server作成する

1. RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー**] ページで [**新規**] をクリックして、次のいずれかを実行します。
    
   - ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。 [**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。
    
   - サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。 サイトの一覧で、対象のサイトをクリックして [**OK**] をクリックします。
    
5. [**説明**] フィールドに、PIN ポリシーの説明を入力します。
    
6. [**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。 既定の最小サイズは 5 桁です。
    
7. ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。
    
8. [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。
    
9. PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。
    
10. [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。
    
11. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。
    
12. PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。
    
    > [!IMPORTANT]
    > セキュリティ上の理由から、一般的なパターンを許可しない方法をお勧めします。 
  
13. [**確定**] をクリックします。
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用してユーザーまたはサイトの PIN Skype for Business Server作成する

ユーザーまたはサイトの PIN ポリシーを作成するには、 **New-CsPinPolicy コマンドレットを使用** します。
  
次のコマンドは、Identity サイト:Redmond を使用して新しい PIN ポリシーを作成します。 このコマンドには、MinPasswordLength プロパティを 7 に設定するために使用される 1 つのオプション パラメーター MinPasswordLength が含まれています。 残りのすべてのポリシー プロパティは、既定値を使用して構成されます。
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 完全な構文の説明とパラメーターの一覧を含む詳細については、「 [New-CsPinPolicy」を参照してください](/powershell/module/skype/new-cspinpolicy?view=skype-ps)。
  
## <a name="modify-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを変更する

ユーザーまたはサイトの PIN ポリシーを変更するには、コントロール Skype for Business Serverを使用するか、管理シェルSkype for Business Server使用します。
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用してユーザーまたはサイトの PIN Skype for Business Server変更する

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー**] ページで、変更する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。
    
5. [**PIN ポリシーの編集**] で、ポリシー名以外のポリシー設定を変更します。ポリシー名は変更できません。
    
6. [**確定**] をクリックします。
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用してユーザーまたはサイトの PIN Skype for Business Server変更する

ダイヤルイン会議 PIN ポリシーを変更するには、 **Set-CsPinPolicy コマンドレットを使用** します。
  
次のコマンドは、Redmond サイトに割り当てられた PIN ポリシーを変更します。 この場合、コマンドは MinPasswordLength プロパティの値を 10 に変更します。つまり、新しい PIN には少なくとも 10 桁の数字が含まれている必要があります。
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

完全な構文の説明とパラメーターの一覧を含む詳細については、「 [Set-CsPinPolicy」を参照してください](/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="delete-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを削除する

ユーザーまたはサイトの PIN ポリシーは、コントロール パネルまたは管理シェルSkype for Business Server使用して削除Skype for Business Serverできます。
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用してユーザーまたはサイトの PIN Skype for Business Server削除する

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。
    
4. [**PIN ポリシー] ページで**、変更する PIN ポリシーをクリックし、[編集] をクリックし、[削除] をクリック **します**。
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用してユーザーまたはサイトの PIN Skype for Business Server削除する

ユーザーまたはサイトの PIN ポリシーを削除するには、 **Remove-CsPinPolicy コマンドレットを使用** します。
  
次のコマンドは、サイト スコープで構成されているすべての PIN ポリシーを削除します。 これを行うには、 **Get-CsPinPolicy** コマンドレットと Filter パラメーターを使用して、"site:" という文字で始まる Identity を持つすべてのポリシーのコレクションを返します。 このコレクションは **Remove-CsPinPolicy** コマンドレットにパイプ処理され、コレクション内の各ポリシーが削除されます。
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

完全な構文の説明とパラメーターの一覧を含む詳細については、「 [Remove-CsPinPolicy」を参照してください](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。
