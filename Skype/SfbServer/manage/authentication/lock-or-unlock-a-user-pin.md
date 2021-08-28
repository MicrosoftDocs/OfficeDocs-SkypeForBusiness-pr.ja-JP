---
title: ユーザーの PIN をロックまたはロック解除Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '概要: ユーザーのダイヤルイン会議 PIN をロックまたはロック解除して、Skype for Business Server。'
ms.openlocfilehash: 8348685e925d9726c43ecd54b6116b9b40652208
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633641"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>ユーザーの PIN をロックまたはロック解除Skype for Business Server
 
**概要:** ユーザーのダイヤルイン会議 PIN をロックまたはロック解除して、Skype for Business Server。
  
[コントロール パネル] の [ユーザー]セクションからユーザーの PIN をロックSkype for Business Server解除できます。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>コントロール パネルでユーザーの PIN をSkype for Business Serverするには

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
    
   d.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e.  [**検索**] をクリックします。
    
   f. ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>[コントロール パネル] でユーザーの PIN をSkype for Business Serverするには

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
    
   d.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e.  [**検索**] をクリックします。
    
   f. ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用してユーザー PIN をロックWindows PowerShellする

ユーザー PIN をロックおよびロック解除するには、Windows PowerShellコマンドレットとLock-CsClientPinをUnlock-CsClientPinします。 これらのコマンドレットは、Skype for Business Server管理シェルから、またはリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した[Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-lock-a-user-pin"></a>ユーザー PIN をロックするには

- ユーザーの PIN をロックするには、次のコマンドレットLock-CsClientPinします。 次に例を示します。
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>ユーザー PIN のロックを解除するには

- ユーザーの PIN のロックを解除するには、次のコマンドレットUnlock-CsClientPinします。 次に例を示します。
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

詳細については [、Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) コマンドレットおよび [Unlock-CsClientPin](/powershell/module/skype/unlock-csclientpin?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。