---
title: エンタープライズ Voip オンプレミスのユーザーを有効にする
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
description: ユーザーが電話システム (クラウド PBX) を使用するには、最初にエンタープライズ Voip に対して有効にし、電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開に所属している間に、オンプレミス展開を使用して実行します。
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359193"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>エンタープライズ Voip オンプレミスのユーザーを有効にする
 
ユーザーが電話システム (クラウド PBX) を使用するには、最初にエンタープライズ Voip に対して有効にし、電話番号を割り当てる必要があります。 これは、ユーザーがオンプレミス展開に所属している間に、オンプレミス展開を使用して実行します。

> [!Important]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、サービスにアクセスできなくなります。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online のどちらを使用しても、オンプレミス環境との間の PSTN 接続がサポートされなくなります。  [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを Teams に接続する方法について説明します。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>エンタープライズ Voip オンプレミスでユーザーを有効にし、電話番号を割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート] メニューまたはデスクトップショートカットを使用して、Skype for Business Server コントロールパネルを開きます。
    
    ブラウザーウィンドウを開き、管理者の URL を入力して Skype for Business Server コントロールパネルを開くこともできます。
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。
    
5. 表で、エンタープライズ Voip を有効にする Skype for Business Online ユーザーアカウントをクリックします。
    
6. [ **編集** ] メニューの [ **詳細の表示**] をクリックします。
    
7. [ **テレフォニー**] で、[ **エンタープライズ voip**] をクリックします。
    
8. [ **回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel: + 14255550200) を入力します。 [ **確定**] をクリックします。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>エンタープライズ Voip オンプレミスでユーザーを有効にするときの特別な考慮事項

場合によっては、エンタープライズ Voip でユーザーを有効にする方法を変更して、確実に通話を発信および受信できるようにする必要があります。 次の条件を満たすユーザーが展開に含まれている場合は、そのユーザーのエンタープライズ Voip を有効にするための手順を実行します。
  
- オンプレミスの AD でユーザーが作成されていて、skype for business または Enterprise Voice が有効になっていない状態で Skype for Business Online と同期されており、LineURI が設定されていない場合は、影響を受けるユーザーごとに次のコマンドレットを実行し、その値を \< \> 環境の実際の値に置き換えます
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーが既にオンプレミスの Skype for business に対して有効になっているが、エンタープライズ Voip が有効になっていない場合、または Skype for Business Online に移動する前に LineURI が割り当てられている場合は、ユーザーごとに次のコマンドレットを実行します。
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- LineURI が既に割り当てられている場合でも、ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ Voip が有効になっていない場合は、影響を受けるユーザーごとに次のコマンドレットを実行します。
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


