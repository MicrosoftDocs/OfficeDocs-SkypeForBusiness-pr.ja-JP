---
title: Skype for Business Server でユーザーの PIN 情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: '概要: Skype for Business Server でユーザーの PIN 情報を表示します。'
ms.openlocfilehash: e0a74d980be4c77c5fe92f9e0d871f238a7271f5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991942"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Skype for Business Server でユーザーの PIN 情報を表示する
 
**概要:** Skype for Business Server でユーザーの PIN 情報を表示します。
  
認証されたユーザーとしてダイヤルイン会議に参加するには、Skype for Business Server ユーザー (Active Directory ドメインサービス (AD DS) の資格情報に暗証番号 (PIN) が必要です。 Skype for Business Server コントロールパネルからユーザーの PIN 情報を表示できます。
  
> [!NOTE]
> PIN が設定されているかどうかや PIN の最終変更日時などの PIN 状態情報を表示することはできますが、PIN の状態を調べても最新の PIN は確認できません。 ユーザーが PIN を紛失した場合は、「 [Skype For Business Server でユーザーのダイヤルイン会議 PIN を設定](set-a-user-s-dial-in-conferencing-pin.md)する」の手順に従ってリセットできます。
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルでユーザーの PIN を表示するには

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
    
    > [!NOTE]
    > PIN がロックされている場合は、ロックを解除しないと PIN を設定できません。PIN のロックを解除するには、ユーザーをクリックし、[**アクション**] をクリックして、[**PIN のロック解除**] をクリックします。 
  
6. 検索結果でユーザーをクリックし、[**アクション**] をクリックして、[**PIN の状態を表示**] をクリックします。
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してユーザーの PIN 情報を表示する

Get-CsClientPinInfo コマンドレットを使用して、ユーザーの PIN 情報を表示できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-view-user-pin-information"></a>ユーザーの PIN 情報を表示するには

ユーザーの PIN 情報を表示するには、Skype for Business Server 管理シェルで次のようなコマンドを入力し、enter キーを押します。
    
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

詳細については、 [CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server でユーザーのダイヤルイン会議の PIN を設定する](set-a-user-s-dial-in-conferencing-pin.md)
  
[Skype for Business Server でユーザー PIN をロックまたはロック解除する](lock-or-unlock-a-user-pin.md)
