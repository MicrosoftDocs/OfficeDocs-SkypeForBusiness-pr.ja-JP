---
title: ユーザー単位の PIN ポリシーをユーザー単位で割り当Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: '概要: AV 証明書と OAuth 証明書をステージにSkype for Business Server。'
ms.openlocfilehash: 51bf650d907923c83801799a28220eae9a1f385c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845480"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>ユーザー単位の PIN ポリシーをユーザー単位で割り当Skype for Business Server

**概要:** AV 証明書と OAuth 証明書をステージSkype for Business Server。
  
ダイヤルイン会議の個人識別番号 (PIN) ポリシーは、ユーザー アカウントの個々の設定の 1 つで、Skype for Business Serverコントロール パネルで構成できます。
  
ユーザーは 1 つまたは複数のユーザー単位の PIN ポリシーを展開できますが、この展開はオプションです。 また、グローバルレベルの PIN ポリシーまたはサイトレベルの PIN ポリシーだけを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、ダイヤルイン会議での PIN の使用に関するユーザーの権限およびアクセス許可により、グローバルレベルの PIN ポリシーで定義された既定の設定が自動的に適用されます。
  
ユーザー単位の PIN ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが作成したか、特定のユーザーが使用する PIN にサーバーが課す制約を指定します。
  
### <a name="to-assign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. ユーザーを探すには、次のどちらかの方法を使用します。
    
   - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
   - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a. [**フィルターの追加**] をクリックします。
    
   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
   c. [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
   d. 選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e. [**検索**] をクリックします。
    
6. 検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。
    
    > [!TIP]
    > 同じユーザー単位の PIN ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[**アクション**] をクリックしてから [**ポリシーの割り当て**] をクリックします。 
  
7. [**ポリシーの割り当て**] の [**PIN ポリシー**] で、次のいずれかの手順を実行します。
    
    > [!NOTE]
    > [ポリシーの割り当て] ダイアログ ボックスを使用して構成できるポリシーは複数あるため、ダイアログ ボックス内のすべてのポリシーで既定 **\<Keep as is\>** で選択されます。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。
  
   - グローバル Skype for Business Serverまたはサイト レベルのポリシーが定義されている場合は、ユーザーが自動的に選択できます。
    
   - [**PIN ポリシー**] ページであらかじめ定義した、ユーザー単位の PIN ポリシーの名前をクリックします。
    
     > [!TIP]
     > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [**表示**] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。
  
8. 終了したら、[**OK**] をクリックします。
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用Per-User PIN ポリシーを割りWindows PowerShellする

ユーザーごとの PIN ポリシーを割り当てるには、Windows PowerShell **Grant-CsPinPolicy コマンドレットを使用** します。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモート サーバーを使用してリモート Windows PowerShell接続する方法Skype for Business Server [Microsoft Lync リモート PowerShell 管理」を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>ユーザー単位の PIN ポリシーを単一のユーザーに割り当てるには

- 次のコマンドは、ユーザー単位の PIN ポリシー RedmondPinPolicy をユーザー「Ken Myer」に割り当てます。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>ユーザー単位の PIN ポリシーを複数のユーザーに割り当てるには

- 次のコマンドは、ユーザー単位の PIN ポリシー RedmondUsersPinPolicy を Redmond 市で働くすべてのユーザーに割り当てます。 このコマンドで使用される LdapFilter パラメーターの詳細については [、「Get-CsUser」を参照してください](/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当て解除するには

- 次のコマンドは、Ken Myer に割り当てられたユーザー単位の PIN ポリシーを割り当て解除します。ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

詳細については [、「Grant-CsPinPolicy」を参照してください](/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。
  
## <a name="see-also"></a>関連項目

[新しい PIN ポリシーを作成Skype for Business Server](create-a-new-pin-policy.md)