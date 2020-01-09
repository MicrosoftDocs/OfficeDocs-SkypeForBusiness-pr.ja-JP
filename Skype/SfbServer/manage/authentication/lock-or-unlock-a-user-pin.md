---
title: Skype for Business Server でユーザー PIN をロックまたはロック解除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議の PIN をロックまたはロック解除します。'
ms.openlocfilehash: bbf082fd85780972387cf014573e22996a9edcf0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992314"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Skype for Business Server でユーザー PIN をロックまたはロック解除する
 
**概要:** Skype for Business Server のユーザーのダイヤルイン会議の PIN をロックまたはロック解除します。
  
Skype for Business Server コントロールパネルの [**ユーザー** ] セクションで、ユーザーの PIN をロックまたはロック解除することができます。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルでユーザーの PIN をロックするには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. ユーザーを探すには、次のいずれかの方法を使用します。
    
    - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。
    
    - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a. [**フィルターの追加**] をクリックします。
    
   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
   c. [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
   d. 選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   •. [**検索**] をクリックします。
    
   f. ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルでユーザーの PIN のロックを解除するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. ユーザーを探すには、次のいずれかの方法を使用します。
    
   - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。
    
   - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a. [**フィルターの追加**] をクリックします。
    
   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
   c. [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
   d. 選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   •. [**検索**] をクリックします。
    
   f. ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したユーザー Pin のロックとロック解除

Windows PowerShell を使用して、ユーザーピンのロックとロック解除を行うことができます。 これらのコマンドレットは、Skype for Business Server 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-lock-a-user-pin"></a>ユーザー PIN をロックするには

- ユーザーの PIN をロックするには、Lock-CsClientPin コマンドレットを使用します。 次に例を示します。
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>ユーザー PIN のロックを解除するには

- ユーザーの PIN のロックを解除するには、[ロック解除] コマンドレットを使用します。 次に例を示します。
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

詳細については、「[ロック-csclientpin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)と[csclientpin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)のコマンドレット」のヘルプトピックを参照してください。
