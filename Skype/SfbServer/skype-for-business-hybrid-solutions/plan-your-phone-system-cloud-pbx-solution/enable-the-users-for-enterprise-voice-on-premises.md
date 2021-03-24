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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: ユーザーが電話システム (Cloud PBX) を使用するには、最初に電話システムで有効にしエンタープライズ VoIP電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開にまだ存在している間に、オンプレミス展開を使用して行います。
ms.openlocfilehash: b26e51ba316c63e0f992b843a7763586d7e9b575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098593"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>オンプレミスでユーザーエンタープライズ VoIP有効にする
 
ユーザーが電話システム (Cloud PBX) を使用するには、最初に電話システムで有効にしエンタープライズ VoIP電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開にまだ存在している間に、オンプレミス展開を使用して行います。

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>オンプレミスのユーザーを有効エンタープライズ VoIP電話番号を割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート] メニューまたはデスクトップ ショートカットを使用して、Skype for Business Server コントロール パネルを開きます。
    
    ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開く方法もできます。
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。
    
5. 表で、Skype for Business Online ユーザー アカウントをクリックして、このユーザー アカウントを有効エンタープライズ VoIP。
    
6. [編集] **メニューの** [詳細の表示 **] をクリックします**。
    
7. [ **テレフォニー] の** 下の [エンタープライズ VoIP] **をクリックします**。
    
8. [ **回線 URI]** をクリックし、正規化された一意の電話番号 (tel:+14255550200 など) を入力します。 次に、[ **コミット] をクリックします**。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>オンプレミスでユーザーを有効にする場合のエンタープライズ VoIP考慮事項

場合によっては、ユーザーが通話を正常に行って受信エンタープライズ VoIPを有効にする方法を変更する必要がある場合があります。 展開内に次の条件を満たすユーザーが含まれている場合は、含まれる手順を実行して、ユーザーが次の条件を満たエンタープライズ VoIP。
  
- ユーザーがオンプレミス AD で作成され、Skype for Business または エンタープライズ VoIP で有効にせずに Skype for Business Online と同期され、LineURI セットがない場合は、影響を受ける各ユーザーに対して次のコマンドレットを実行し、環境の実際の値で値を置き換えます \< \> 。
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ VoIP で有効になっていないか、Skype for Business Online に移動する前に LineURI が割り当てられていない場合は、各ユーザーに対して次のコマンドレットを実行します。
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ VoIP に対して有効になっていない場合は、LineURI が既に割り当てられている場合でも、影響を受ける各ユーザーに対して次のコマンドレットを実行します。
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```