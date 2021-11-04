---
title: '[ユーザーの PIN 情報を表示する] Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: '概要: ユーザーの PIN 情報をユーザーに表示Skype for Business Server。'
ms.openlocfilehash: 9135a502879f3d6d28c2aab9fbdbf81e9d399e29
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765505"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>[ユーザーの PIN 情報を表示する] Skype for Business Server
 
**概要:**[ユーザーの PIN 情報を表示する] Skype for Business Server。
  
認証されたユーザーとしてダイヤルイン会議に参加するには、Active Directory ドメイン サービス (AD DS) 資格情報を持つ Skype for Business Server ユーザーに個人識別番号 (PIN) が必要です。 コントロール パネルからユーザーの PIN 情報Skype for Business Server表示できます。
  
> [!NOTE]
> PIN が設定されているかどうかや PIN の最終変更日時などの PIN 状態情報を表示することはできますが、PIN の状態を調べても最新の PIN は確認できません。 ユーザーが PIN を紛失した場合は、「ユーザーのダイヤルイン会議 PIN を設定する」の手順に従って[、PIN](set-a-user-s-dial-in-conferencing-pin.md)をリセットSkype for Business Server
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>[コントロール パネル] でユーザーの PIN Skype for Business Serverするには

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
    
   d. 選択したユーザー プロパティに応じて、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。
    
    > [!TIP]
    > クエリにその他の検索句を追加するには、[**フィルターの追加**] をクリックします。 
  
   e. [**検索**] をクリックします。
    
    > [!NOTE]
    > PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。PIN のロックを解除するには、ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。 
  
6. 検索結果でユーザーをクリックし、[**アクション**] をクリックして、[**PIN の状態を表示**] をクリックします。
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>ユーザーの PIN 情報を表示する方法 (Windows PowerShellコマンドレットを使用)

Get-CsClientPinInfo コマンドレットを使用して、ユーザーの PIN 情報を表示できます。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-view-user-pin-information"></a>ユーザーの PIN 情報を表示するには

ユーザーの PIN 情報を表示するには、次のようなコマンドを [管理シェル] に入力Skype for Business Server Enter キーを押します。
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

次のような情報が表示されます。

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

詳細については [、Get-CsConferenceDisclaimer コマンドレットのヘルプ トピックを参照](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) してください。
  
## <a name="see-also"></a>関連項目

[ユーザーのダイヤルイン会議の PIN を設定Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[ユーザーの PIN をロックまたはロック解除Skype for Business Server](lock-or-unlock-a-user-pin.md)