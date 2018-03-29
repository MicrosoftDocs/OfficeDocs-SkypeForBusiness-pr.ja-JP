---
title: Skype for Business Server 2015 でのユーザー PIN のロックまたはロック解除
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: '概要: ロックまたはビジネス サーバー 2015 の Skype のユーザーのダイヤルイン会議 PIN のロックを解除します。'
ms.openlocfilehash: 5bd4a334f9c0b543d9b4cade8631f992a920dfb1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのユーザー PIN のロックまたはロック解除
 
**の概要:**ロックまたはビジネス サーバー 2015 の Skype のユーザーのダイヤルイン会議 PIN のロックを解除します。
  
ビジネス サーバーのコントロール パネルの Skype の**ユーザー** ] セクションから、ユーザーの PIN をロック解除またはロックできます。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype のビジネス サーバーのコントロール パネルのユーザーの暗証番号 (pin) をロックするのには

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
    
   d. 選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e。 [**検索**] をクリックします。
    
   f。 ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック**] をクリックします。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype でのユーザーの暗証番号 (pin) のロックを解除するには

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
    
   d. 選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e。 [**検索**] をクリックします。
    
   f。 ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザー Pin のロックとロック解除

ロックし、Windows PowerShell と - CsClientPin のロックとロック解除 CsClientPin コマンドレットを使用してユーザー Pin のロックを解除できます。 実行できますこれらのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-lock-a-user-pin"></a>ユーザー PIN をロックするには

- ユーザーの暗証番号 (pin) をロックするには、ロック CsClientPin コマンドレットを使用します。 次に例を示します。
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>ユーザー PIN のロックを解除するには

- ユーザーの暗証番号 (pin) のロックを解除するには、ロック解除 CsClientPin コマンドレットを使用します。 例:
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

詳細については、 [- CsClientPin のロック](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)と[ロック解除 CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。