---
title: Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を設定します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: '概要: は、Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を設定します。'
ms.openlocfilehash: 62b38b8ef15aa2283b66fc18abf5ec0e84e64870
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217902"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を設定します。
 
**の概要:** Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を設定します。
  
として認証されたユーザーのダイヤルイン会議に参加するには、ビジネス サーバーのユーザーを Active Directory ドメイン サービス (AD DS) の資格情報は、Skype には、暗証番号 (PIN) が必要です。 ユーザーはダイヤルイン会議の PIN を忘れた場合や、ビジネス サーバーの Skype を使用して PIN を設定できませんが、Skype からビジネス サーバーのコントロール パネルのユーザーの PIN を設定できます。 PIN は自動で生成することも手動で作成することもできます。
  
> [!NOTE]
> 最小サイズなど、PIN の具体的な特性は、ポリシーとして構成できます。グローバル ポリシーに加えて、個々のサイトまたはユーザーを対象にした PIN ポリシーを構成できます。 
  
### <a name="to-set-a-users-pin"></a>ユーザーの暗証番号 (pin) を設定するのには

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
    
    > [!NOTE]
    > PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。PIN のロックを解除するには、ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。 
  
6. 検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**暗証番号 (PIN) の設定**] をクリックします。
    
7. [**暗証番号 (PIN) の設定**] ダイアログ ボックスで、次のどちらかの手順を実行します。
    
   - Skype ビジネスのサーバー ユーザーの暗証番号 (pin) を生成するを許可するには、(既定値) **、有効な暗証番号 (pin) を自動的に生成**を選択します。
    
   - 自分の PIN を作成するには、[**特定の PIN を手動で入力**] をクリックして、テキスト ボックスをクリックし、PIN のポリシー設定で指定されている PIN の要件を満たす PIN を入力します。
    
8. [**OK**] をクリックします。
    
9. [**暗証番号 (PIN) の設定**] で、次のどちらかの手順を実行します。 
    
   - [**PIN の表示**] チェック ボックスをオンにして PIN を表示し、PIN をコピーし、組織で推奨される方法を使用しているユーザーに伝えます。
    
   - PIN を電子メールで送信するには、[**新しい PIN をユーザーに送信するために電子メール アプリケーションを開く**] をクリックします。使用している電子メール クライアントが Microsoft Office Outlook の場合、PIN は新しい電子メール メッセージに自動的にコピーされます。他の電子メール クライアントを使用している場合は、[**PIN の表示**] チェック ボックスをオンにして PIN を表示し、電子メール メッセージにコピーしてください。
    
10. [**閉じる**] をクリックします。
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーの暗証番号 (pin) を割り当てること。

Set-CsClientPin コマンドレットを使用して、PIN 番号を割り当てることができます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>PIN 番号をユーザーに割り当てるには

次のコマンドでは、PIN 番号を Ken Myer というユーザーに割り当てます。 暗証番号 (pin) のパラメーターが含まれないため、Skype ビジネス サーバーに自動的に生成し、暗証番号 (PIN) を割り当てます。
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>特定の PIN 番号をユーザーに割り当てるには

このコマンドでは、Pin パラメーターを使用して PIN 番号 121989 を Ken Myer というユーザーに割り当てます。
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

詳細については、[セット CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

