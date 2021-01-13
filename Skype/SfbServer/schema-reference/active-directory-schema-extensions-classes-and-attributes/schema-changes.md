---
title: Skype for Business Server でのスキーマの変更点
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメイン サービスを準備する必要があります。 スキーマ拡張機能は、Skype for Business Server に必要なクラスと属性を追加します。
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813577"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Skype for Business Server でのスキーマの変更点
 
Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメイン サービスを準備する必要があります。 スキーマ拡張機能は、Skype for Business Server に必要なクラスと属性を追加します。

> [!NOTE]
> Lync Server 2013 から Skype for Business Server 2015 にアップグレードする場合、スキーマは変更されないので、この記事は適用されません。
  
Skype for Business Server は、いくつかの新しいクラスと属性を必要とし、いくつかの既存のクラスと属性を変更します。 さらに、Skype for Business Server の多くの構成情報は、以前のバージョンと同様に、AD DS ではなく中央管理ストアに格納されます。 次の情報は、Skype for Business Server AD DS に保存されます。
  
- **スキーマ拡張**:
    
  - ユーザー オブジェクトの拡張
    
  - サポートされている以前のバージョンの Lync Server との下位互換性を維持するためのクラスの拡張機能。
    
- **データ** (Skype for Business Server の拡張スキーマと既存のスキーマ クラスに格納されます):
    
  - ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定
    
  - リソース グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
  - 中央管理ストアへのポインター
    
  - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)
    
このトピックでは、Skype for Business Server に必要な Active Directory スキーマの変更点について説明します。 以前のバージョンの Communications Server で導入されたスキーマの変更Officeしません。 クラスとその説明の一覧については、Skype for Business Server のスキーマ クラスと [説明を参照してください](schema-classes-and-descriptions.md)。 属性とその説明の一覧については、Skype for Business Server のスキーマ属性と [説明を参照してください](schema-attributes-and-descriptions.md)。 含め得る属性を持つクラスの一覧については、Skype for Business Server のクラス別の [スキーマ属性を参照してください](schema-attributes-by-class.md)。
  
msRTCSIP プレフィックスは、Skype for Business Server に固有のクラスと属性を識別します。
  
## <a name="new-active-directory-attributes"></a>新規 Active Directory 属性

次の表では、Skype for Business Server によって追加される Active Directory 属性について説明します。
  
**Skype for Business Server によって追加される属性**

|**属性**|**説明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。 この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。 この属性は Exchange 2013 と共有されます。  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |この属性は、フロントエンド プールで使用SQL Serverミラー化されたバックエンドを格納するために使用されます。  <br/> |
   
## <a name="modified-active-directory-classes"></a>変更された Active Directory クラス

次の表では、Skype for Business Server によって変更される Active Directory クラスについて説明します。
  
**Skype for Business Server によって変更されるクラス**

|**クラス**|**変更**|**クラスまたは属性**|
|:-----|:-----|:-----|
|User  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add:mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

