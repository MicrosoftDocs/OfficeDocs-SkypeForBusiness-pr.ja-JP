---
title: Skype for Business Server 2015 でのユーザー単位の PIN ポリシーの割り当て
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: '概要: ステージの AV と OAuth の証明書サーバー 2015 のビジネス用の Skype のです。'
ms.openlocfilehash: a103d6463a02cd00d71769b8f86b43fae514a19d
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504958"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのユーザー単位の PIN ポリシーの割り当て

**の概要:** ステージ AV と OAuth の証明書サーバー 2015 のビジネス用の Skype のです。
  
ダイヤルイン会議の個人識別番号 (PIN) ポリシーは、個々 のビジネス サーバーのコントロール パネルの Skype で構成可能なユーザー アカウントの設定のいずれかです。
  
ユーザーは 1 つまたは複数のユーザー単位の PIN ポリシーを展開できますが、この展開はオプションです。また、グローバルレベルの PIN ポリシーまたはサイトレベルの PIN ポリシーだけを展開することもできます。ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、ダイヤルイン会議での PIN の使用に関するユーザーの権限およびアクセス許可により、グローバルレベルの PIN ポリシーで定義された既定の設定が自動的に適用されます。
  
ユーザー単位の PIN ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが作成したか、特定のユーザーが使用する PIN にサーバーが課す制約を指定します。
  
### <a name="to-assign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. ユーザーを探すには、次のいずれかの方法を使用します。
    
   - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。
    
   - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a. [**フィルターの追加**] をクリックします。
    
   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
   c. [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
   d. 選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e。 [**検索**] をクリックします。
    
6. 検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。
    
    > [!TIP]
    > 同じユーザー単位の PIN ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[**アクション**] をクリックしてから [**ポリシーの割り当て**] をクリックします。 
  
7. [**ポリシーの割り当て**] の [**PIN ポリシー**] で、次のいずれかの手順を実行します。
    
    > [!NOTE]
    > **ポリシーの割り当て**] ダイアログ ボックスを使用して構成することができます複数のポリシーがあるため**\<は、してください\>** のすべてのポリシー] ダイアログ ボックスで既定で選択します。 この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。
  
   - Skype ビジネス サーバーの 2015 グローバル レベルのポリシーを自動的に選択するを許可するか、サイト レベルのポリシーを定義します。
    
   - [**PIN ポリシー**] ページであらかじめ定義した、ユーザー単位の PIN ポリシーの名前をクリックします。
    
     > [!TIP]
     > 割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [**表示**] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。
  
8. 終了したら、[**OK**] をクリックします。
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、ユーザー単位の PIN ポリシーを割り当てる

Windows PowerShell と**与える CsPinPolicy**コマンドレットを使用してユーザー単位の PIN ポリシーを割り当てることができます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行することができます。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>ユーザー単位の PIN ポリシーを単一のユーザーに割り当てるには

- 次のコマンドは、ユーザー単位の PIN ポリシー RedmondPinPolicy をユーザー「Ken Myer」に割り当てます。
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>ユーザー単位の PIN ポリシーを複数のユーザーに割り当てるには

- 次のコマンドは、ユーザー単位の PIN ポリシー RedmondUsersPinPolicy を Redmond 市で働くすべてのユーザーに割り当てます。 詳細については、このコマンドで使用される、LdapFilter パラメーターは、 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)を参照してください。
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>ユーザー単位の PIN ポリシーを割り当て解除するには

- 次のコマンドは、Ken Myer に割り当てられたユーザー単位の PIN ポリシーを割り当て解除します。ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

詳細については、[補助金 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)を参照してください。
  
## <a name="see-also"></a>関連項目

[ビジネス サーバー 2015 の Skype の新しい暗証番号 (pin) ポリシーを作成する.](create-a-new-pin-policy.md)