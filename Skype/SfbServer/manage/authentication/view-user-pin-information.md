---
title: ユーザー暗証番号 (pin) について、Skype のビジネス サーバーの表示
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: '概要: は、Skype のビジネス サーバーのユーザーの暗証番号 (pin) の情報を表示します。'
ms.openlocfilehash: 4b0eda76e4429ee5c6d658f4d161783bc4d356a3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21008560"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>ユーザー暗証番号 (pin) について、Skype のビジネス サーバーの表示
 
**の概要:** ユーザー暗証番号 (pin) について、Skype のビジネスのサーバーを表示します。
  
として認証されたユーザーのダイヤルイン会議に参加するには、ビジネス サーバーのユーザーを Active Directory ドメイン サービス (AD DS) の資格情報は、Skype には、暗証番号 (PIN) が必要です。 ビジネス サーバーのコントロール パネルの Skype からのユーザーの暗証番号 (pin) の情報を表示することができます。
  
> [!NOTE]
> PIN が設定されているかどうかや PIN の最終変更日時などの PIN 状態情報を表示することはできますが、PIN の状態を調べても最新の PIN は確認できません。 ユーザーが PIN を失った場合は、[ユーザーのダイヤルイン会議 Business Server の Skype では、暗証番号 (pin) の設定](set-a-user-s-dial-in-conferencing-pin.md)の手順に従ってリセットできます。
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype のビジネス サーバーのコントロール パネルのユーザーの暗証番号 (pin) を表示するのには

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
  
6. 検索結果でユーザーをクリックし、[**アクション**] をクリックして、[**PIN の状態を表示**] をクリックします。
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>使用して Windows PowerShell コマンドレットがユーザーの PIN 情報を表示します。

Get-CsClientPinInfo コマンドレットを使用して、ユーザーの PIN 情報を表示できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-view-user-pin-information"></a>ユーザーの PIN 情報を表示するには

ユーザーの PIN 情報を表示するのには、Skype でビジネス サーバー管理シェルの次のようなコマンドを入力し、ENTER キーを押します。
    
  ```
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

詳細については、 [Get CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  
## <a name="see-also"></a>関連項目

[Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を設定します。](set-a-user-s-dial-in-conferencing-pin.md)
  
[ロックまたはビジネスのサーバーのユーザーの Skype では、暗証番号 (pin) のロックを解除](lock-or-unlock-a-user-pin.md)