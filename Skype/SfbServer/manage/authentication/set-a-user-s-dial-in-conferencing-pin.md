---
title: Skype for Business Server でユーザーのダイヤルイン会議 PIN を設定する
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議 PIN を設定します。'
ms.openlocfilehash: c34e895471fdffb13a4cdb10806bd07146474e44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119556"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Skype for Business Server でユーザーのダイヤルイン会議 PIN を設定する
 
**概要:** Skype for Business Server のユーザーのダイヤルイン会議 PIN を設定します。
  
認証されたユーザーとしてダイヤルイン会議に参加するには、Active Directory ドメイン サービス (AD DS) 資格情報を持つ Skype for Business Server ユーザーに個人識別番号 (PIN) が必要です。 ユーザーがダイヤルイン会議 PIN を忘れた場合、または Skype for Business Server を使用して PIN を設定していない場合は、Skype for Business Server コントロール パネルからユーザーの PIN を設定できます。 PIN は自動で生成することも手動で作成することもできます。
  
> [!NOTE]
> 最小サイズなど、PIN の具体的な特性は、ポリシーとして構成できます。 グローバル ポリシーに加えて、個々のサイトまたはユーザーを対象にした PIN ポリシーを構成できます。 
  
### <a name="to-set-a-users-pin"></a>ユーザーの PIN を設定するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. ユーザーを探すには、次のどちらかの方法を使用します。
    
   - [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。
    
   - 保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a. [**フィルターの追加**] をクリックします。
    
   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。
    
   c. [**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。
    
   d. 選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e. [**検索**] をクリックします。
    
    > [!NOTE]
    > PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。 PIN のロックを解除するには、ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。 
  
6. 検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**暗証番号 (PIN) の設定**] をクリックします。
    
7. [**暗証番号 (PIN) の設定**] ダイアログ ボックスで、次のどちらかの手順を実行します。
    
   - Skype for Business Server でユーザーの PIN の生成を許可するには、[有効な PIN を **自動的** に生成する ] (既定) を選択します。
    
   - 自分の PIN を作成するには、[**特定の PIN を手動で入力**] をクリックして、テキスト ボックスをクリックし、PIN のポリシー設定で指定されている PIN の要件を満たす PIN を入力します。
    
8. [**OK**] をクリックします。
    
9. [**暗証番号 (PIN) の設定**] で、次のどちらかの手順を実行します。 
    
   - [**PIN の表示**] チェック ボックスをオンにして PIN を表示し、PIN をコピーし、組織で推奨される方法を使用しているユーザーに伝えます。
    
   - PIN を電子メールで送信するには、[**新しい PIN をユーザーに送信するために電子メール アプリケーションを開く**] をクリックします。 使用している電子メール クライアントが Microsoft Office Outlook の場合、PIN は新しい電子メール メッセージに自動的にコピーされます。 他の電子メール クライアントを使用している場合は、[**PIN の表示**] チェック ボックスをオンにして PIN を表示し、電子メール メッセージにコピーしてください。
    
10. [**閉じる**] をクリックします。
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用してユーザー PIN を割りWindows PowerShellする

PIN 番号は、このコマンドレットを使用して割り当Set-CsClientPinすることもできます。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>PIN 番号をユーザーに自動割り当てるには

次のコマンドでは、PIN 番号を Ken Myer というユーザーに割り当てます。 Pin パラメーターは含まれていないため、Skype for Business Server は PIN 番号を自動的に生成して割り当てします。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>特定の PIN 番号をユーザーに割り当てるには

このコマンドでは、Pin パラメーターを使用して PIN 番号 121989 を Ken Myer というユーザーに割り当てます。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

詳細については [、Set-CsClientPin](/powershell/module/skype/set-csclientpin?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
