---
title: 設置型のエンタープライズ VoIP のユーザーを有効にします。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 電話システムを使用して、Office 365 (クラウド PBX) でユーザーが、最初にエンタープライズ VoIP を有効にして、電話番号を割り当てる必要があります。 これを行う設置型展開で、ユーザーのホームでも、設置型の展開を使用しています。
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657448"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>設置型のエンタープライズ VoIP のユーザーを有効にします。
 
電話システムを使用して、Office 365 (クラウド PBX) でユーザーが、最初にエンタープライズ VoIP を有効にして、電話番号を割り当てる必要があります。 これを行う設置型展開で、ユーザーのホームでも、設置型の展開を使用しています。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>設置型のエンタープライズ VoIP に対してユーザーを有効にすると、電話番号を割り当てる

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. スタート メニューかデスクトップ ショートカットを使用して、Skype for Business Server のコントロール パネルを開きます。
    
    また、ブラウザー ウィンドウを開いて管理 URL を入力し、Skype for Business Server のコントロール パネルを開くこともできます。
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。
    
5. テーブルでは、エンタープライズ VoIP を有効にするオンライン ビジネスのユーザー アカウントの Skype をクリックします。
    
6. [**編集**] メニューの [**詳細の表示**] をクリックします。
    
7. [**テレフォニー**] の [**エンタープライズ VoIP**] をクリックします。
    
8. [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力して、[**確定**] をクリックします。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>設置型のエンタープライズ VoIP に対してユーザーを有効にするときに特別な考慮事項

場合によっては、エンタープライズ VoIP でユーザーを有効にする方法を変更して、ユーザーが正常に発信および受信できることを確認する必要があります。 次の条件を満たす、展開内のユーザーがある場合は場合、は、エンタープライズ VoIP に対してユーザーを有効にするのには含まれている手順を実行します。
  
- 設置型で、ユーザーが作成されたかどうかは AD とは、Skype のビジネスやエンタープライズ VoIP に有効にすることがなく、オンライン ビジネスの Skype と同期し、LineURI 設定、影響を受けるユーザーごとの値を置き換えるには、次のコマンドレットを実行する必要はありません <c0 > <b1></b1> 、環境の実際の値とします。
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザー設置型では、ビジネス用の Skype は既に有効になってくださいが、エンタープライズ VoIP を有効になっているかいたビジネス オンラインの Skype を移動する前に、LineURI を割り当てられている場合、は、ユーザーごとに次のコマンドレットを実行します。
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーは、社内のビジネスのための Skype で既に有効になってが有効になっていないエンタープライズ VoIP を LineURI を既に割り当てられている場合でも、影響を受けるユーザーごとに次のコマンドレットを実行します。
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


