---
title: Skype for Business Serverでユーザーごとの PIN ポリシーを割り当てる
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
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: '概要: Skype for Business Serverのユーザーにユーザーごとの PIN ポリシーを割り当てます。'
ms.openlocfilehash: 26df2323647f295c7a1fbff41efbeae3e12b151f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675509"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Skype for Business Serverでユーザーごとの PIN ポリシーを割り当てる

**概要：** Skype for Business Serverの AV 証明書と OAuth 証明書をステージングします。

ダイヤルイン会議の個人識別番号 (PIN) ポリシーは、Skype for Business Server コントロール パネルで構成できるユーザー アカウントの個々の設定の 1 つです。

ユーザーは 1 つまたは複数のユーザー単位の PIN ポリシーを展開できますが、この展開はオプションです。 また、グローバルレベルの PIN ポリシーまたはサイトレベルの PIN ポリシーだけを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、ダイヤルイン会議での PIN の使用に関するユーザーの権限およびアクセス許可により、グローバルレベルの PIN ポリシーで定義された既定の設定が自動的に適用されます。

ユーザー単位の PIN ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが作成したか、特定のユーザーが使用する PIN にサーバーが課す制約を指定します。

## <a name="to-assign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理 URL を入力してSkype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. ユーザーを探すには、次のどちらかの方法を使用します。

   - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

   - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。

5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。

   a.  [**フィルターの追加**] をクリックします。

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
    > [ポリシーの **割り当て** ] ダイアログ ボックスを使用して構成できるポリシーは複数あるため、 **\<Keep as is\>** ダイアログ ボックス内のすべてのポリシーに対して既定で選択されます。 この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。

   - Skype for Business Serverが自動的にグローバル レベルのポリシーを選択するか、定義されている場合はサイト レベルのポリシーを選択できるようにします。

   - [**PIN ポリシー**] ページであらかじめ定義した、ユーザー単位の PIN ポリシーの名前をクリックします。

     > [!TIP]
     > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [**表示**] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。

8. 終了したら、[**OK**] をクリックします。

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したPer-User PIN ポリシーの割り当て

Windows PowerShellと **Grant-CsPinPolicy** コマンドレットを使用して、ユーザーごとの PIN ポリシーを割り当てることができます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモート Windows PowerShellを使用してSkype for Business Serverに接続する方法の詳細については、「[Microsoft Lync Remote PowerShell 管理」を](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)参照してください。 このプロセスは、Skype for Business Serverでも同じです。

### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>ユーザー単位の PIN ポリシーを単一のユーザーに割り当てるには

- 次のコマンドは、ユーザー単位の PIN ポリシー RedmondPinPolicy をユーザー「Ken Myer」に割り当てます。

  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>ユーザー単位の PIN ポリシーを複数のユーザーに割り当てるには

- 次のコマンドは、ユーザー単位の PIN ポリシー RedmondUsersPinPolicy を Redmond 市で働くすべてのユーザーに割り当てます。 このコマンドで使用される LdapFilter パラメーターの詳細については、「 [Get-CsUser](/powershell/module/skype/get-csuser)」を参照してください。

  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当て解除するには

- 次のコマンドは、Ken Myer に割り当てられたユーザー単位の PIN ポリシーを割り当て解除します。ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。

  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

詳細については、「 [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy)」を参照してください。

## <a name="see-also"></a>関連項目

[Skype for Business Serverで新しい PIN ポリシーを作成する](create-a-new-pin-policy.md)
