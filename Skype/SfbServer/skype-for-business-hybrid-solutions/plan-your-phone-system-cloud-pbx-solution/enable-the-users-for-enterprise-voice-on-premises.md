---
title: オンプレミスのエンタープライズボイスのユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
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
description: ユーザーが Office 365 (クラウド PBX) で電話システムを使用するには、まず、エンタープライズボイスで電話システムを有効にして、電話番号を割り当てる必要があります。 これは、オンプレミスの展開を使用して、ユーザーがオンプレミスの展開をホームにしている場合に行われます。
ms.openlocfilehash: fdd405d84cddcfe805063287b8330ccea43397de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287511"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>オンプレミスのエンタープライズボイスのユーザーを有効にする
 
ユーザーが Office 365 (クラウド PBX) で電話システムを使用するには、まず、エンタープライズボイスで電話システムを有効にして、電話番号を割り当てる必要があります。 これは、オンプレミスの展開を使用して、ユーザーがオンプレミスの展開をホームにしている場合に行われます。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>エンタープライズ Voip のユーザーをオンプレミスにして電話番号を割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. スタート メニューかデスクトップ ショートカットを使用して、Skype for Business Server のコントロール パネルを開きます。
    
    また、ブラウザー ウィンドウを開いて管理 URL を入力し、Skype for Business Server のコントロール パネルを開くこともできます。
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。
    
5. 表で、エンタープライズ Voip を有効にする Skype for Business Online のユーザーアカウントをクリックします。
    
6. [**編集**] メニューの [**詳細の表示**] をクリックします。
    
7. [**テレフォニー**] の [**エンタープライズ VoIP**] をクリックします。
    
8. [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力して、[**確定**] をクリックします。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>エンタープライズボイスのオンプレミスのユーザーを有効にするときの特別な考慮事項

場合によっては、エンタープライズ VoIP でユーザーを有効にする方法を変更して、ユーザーが正常に発信および受信できることを確認する必要があります。 次の条件を満たすユーザーが展開に含まれている場合は、エンタープライズ Voip のユーザーを有効にするための手順を実行します。
  
- ユーザーがオンプレミスの広告で作成されていて、Skype for business またはエンタープライズ Voip を有効にせずに、Skype for Business Online と同期していて、LineURI が設定されていない場合は、影響を受けるユーザーごとに次のコマンドレットを実行します。c0 > \> : 環境の実際の値を指定します。
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーがオンプレミスの Skype for Business に対して既に有効になっているが、エンタープライズ Voip では有効になっていない場合、または LineURI を割り当ててから Skype for Business Online に移行している場合は、ユーザーごとに次のコマンドレットを実行します。
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- ユーザーがオンプレミスの Skype for Business で既に有効になっているが、エンタープライズ Voip に対して有効になっていない場合は、既に LineURI が割り当てられていても、次のコマンドレットを実行します。
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


