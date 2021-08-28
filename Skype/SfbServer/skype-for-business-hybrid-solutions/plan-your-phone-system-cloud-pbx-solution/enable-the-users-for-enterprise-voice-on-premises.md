---
title: オンプレミスでユーザーエンタープライズ VoIP有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: ユーザーがクラウド PBX (Cloud PBX) を電話システムするには、最初にユーザーに対して有効にしエンタープライズ VoIP電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開にまだ存在している間に、オンプレミス展開を使用して行います。
ms.openlocfilehash: 28943670a0919d80c96c97b7574cdc82ac68cfde
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613696"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>オンプレミスでユーザーエンタープライズ VoIP有効にする
 
ユーザーがクラウド PBX (Cloud PBX) を電話システムするには、最初にユーザーに対して有効にしエンタープライズ VoIP電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開にまだ存在している間に、オンプレミス展開を使用して行います。

> [!Important]
> Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、オンプレミス環境間の PSTN 接続は、Skype for Business Server または Cloud Connector Edition と Skype for Business Online の間でサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークをネットワークにTeams[する方法について説明します](/MicrosoftTeams/direct-routing-landing-page)。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>オンプレミスのユーザーを有効エンタープライズ VoIP電話番号を割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [デスクトップ] スタート メニューまたはデスクトップ ショートカットを使用して、[コントロール パネル] Skype for Business Server開きます。
    
    ブラウザー ウィンドウを開き、[管理者 URL] を入力して[コントロール パネル] Skype for Business Server開きます。
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。
    
5. 表の [オンライン] ユーザー Skype for Businessをクリックします。このアカウントを有効エンタープライズ VoIP。
    
6. [編集] **メニューの** [詳細の表示 **] をクリックします**。
    
7. [**テレフォニー] の** 下の [エンタープライズ VoIP]**をクリックします**。
    
8. [ **回線 URI]** をクリックし、正規化された一意の電話番号 (tel:+14255550200) を入力します。 次に、[ **コミット] をクリックします**。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>オンプレミスでユーザーを有効にする場合のエンタープライズ VoIP考慮事項

場合によっては、ユーザーが通話を正常に行って受信エンタープライズ VoIPを有効にする方法を変更する必要があります。 展開内に次の条件を満たすユーザーが含まれている場合は、含まれる手順を実行して、ユーザーが次の条件を満たエンタープライズ VoIP。
  
- ユーザーがオンプレミス AD で作成され、Skype for Business または エンタープライズ VoIP で有効にされることなく Skype for Business Online と同期され、LineURI セットがない場合は、影響を受ける各ユーザーに対して次のコマンドレットを実行し、環境の実際の値で値を置き換えます \< \> 。
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ VoIP に対して有効になっていないか、Skype for Business Online に移動する前に LineURI が割り当てられていない場合は、各ユーザーに対して次のコマンドレットを実行します。
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ VoIP に対して有効になっていない場合は、LineURI が既に割り当てられている場合でも、影響を受ける各ユーザーに対して次のコマンドレットを実行します。
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```