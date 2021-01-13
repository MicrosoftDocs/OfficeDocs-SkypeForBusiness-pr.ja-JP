---
title: Skype for Business Server でユーザー PIN をロックまたはロック解除する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議 PIN をロックまたはロック解除します。'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828367"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Skype for Business Server でユーザー PIN をロックまたはロック解除する
 
**概要:** Skype for Business Server のユーザーのダイヤルイン会議 PIN をロックまたはロック解除します。
  
ユーザーの PIN は、Skype for Business Server コントロール パネルの **[ユーザー** ] セクションからロックまたはロック解除できます。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルでユーザーの PIN をロックするには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. ユーザーを探すには、次のどちらかの方法を使用します。
    
    - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
    - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a.  [**フィルターの追加**] をクリックします。
    
   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
   c. [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
   d.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e.  [**検索**] をクリックします。
    
   f. ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルでユーザーの PIN のロックを解除するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. ユーザーを探すには、次のどちらかの方法を使用します。
    
   - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
   - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a.  [**フィルターの追加**] をクリックします。
    
   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
   c. [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
   d.  選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e.  [**検索**] をクリックします。
    
   f. ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したユーザー PIN のロックWindows PowerShell解除

ユーザー PIN のロックとロック解除は、Windows PowerShellコマンドレットと Lock-CsClientPinコマンドレットUnlock-CsClientPinできます。 これらのコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 プロセスは Skype for Business Server でも同じです。
  
### <a name="to-lock-a-user-pin"></a>ユーザー PIN をロックするには

- ユーザーの PIN をロックするには、次のコマンドレットLock-CsClientPinします。 次に例を示します。
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>ユーザー PIN のロックを解除するには

- ユーザーの PIN のロックを解除するには、次のコマンドレットUnlock-CsClientPinします。 例:
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

詳細については [、Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) コマンドレットと [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
