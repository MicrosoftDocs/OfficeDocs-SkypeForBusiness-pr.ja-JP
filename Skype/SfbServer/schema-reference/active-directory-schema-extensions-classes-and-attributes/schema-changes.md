---
title: スキーマの変更Skype for Business Server
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
ms.localizationpriority: medium
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: サーバーを展開して操作するSkype for Business Server、スキーマを拡張して Active Directory ドメイン サービスを準備する必要があります。 スキーマ拡張機能は、ユーザーに必要なクラスと属性をSkype for Business Server。
ms.openlocfilehash: 16f71b80864fae8fc97b87eda22ad2a9594c3987
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626539"
---
# <a name="schema-changes-in-skype-for-business-server"></a>スキーマの変更Skype for Business Server
 
サーバーを展開して操作するSkype for Business Server、スキーマを拡張して Active Directory ドメイン サービスを準備する必要があります。 スキーマ拡張機能は、ユーザーに必要なクラスと属性をSkype for Business Server。

> [!NOTE]
> Lync Server 2013 から Skype for Business Server 2015 にアップグレードする場合は、スキーマの変更は行われたため、この記事は適用されません。
  
Skype for Business Serverいくつかの新しいクラスと属性が必要であり、いくつかの既存のクラスと属性を変更します。 さらに、以前のバージョンと同様Skype for Business Server DS ではなく、サーバーの全体管理ストアにAD構成情報が格納されます。 次の情報は、引き続き DS ADに格納Skype for Business Server。
  
- **スキーマ拡張**:
    
  - ユーザー オブジェクトの拡張
    
  - サポートされている以前のバージョンの Lync Server との下位互換性を維持するためのクラスの拡張機能。
    
- **データ**(拡張スキーマSkype for Business Server既存のスキーマ クラスに格納されます)。
    
  - ユーザーの SIP URI (Uniform Resource Identifier) と他のユーザー設定
    
  - リソース グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
  - 中央管理ストアへのポインター
    
  - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)
    
このトピックでは、ユーザーが必要とする Active Directory スキーマの変更Skype for Business Server。 以前のバージョンのコミュニケーション サーバーで導入されたスキーマの変更Officeしません。 クラスとその説明の一覧については、「[スキーマ](schema-classes-and-descriptions.md)クラスと説明」を参照Skype for Business Server。 属性とその説明の一覧については、「[スキーマ](schema-attributes-and-descriptions.md)の属性と説明」を参照Skype for Business Server。 含まれる可能性のある属性を持つクラスの一覧については、「[スキーマ属性」](schema-attributes-by-class.md)を参照Skype for Business Server。
  
msRTCSIP プレフィックスは、ユーザーに固有のクラスと属性Skype for Business Server。
  
## <a name="new-active-directory-attributes"></a>新規 Active Directory 属性

次の表に、ユーザーが追加する Active Directory 属性Skype for Business Server。
  
**ユーザーが追加した属性Skype for Business Server**

|**属性**|**説明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。 この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。 この属性は、2013 年Exchange共有されます。  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |この属性は、フロントエンド プールで使用SQL Serverミラー化されたバックエンドを格納するために使用されます。  <br/> |
   
## <a name="modified-active-directory-classes"></a>変更された Active Directory クラス

次の表に、ユーザーが変更した Active Directory クラスSkype for Business Server。
  
**クラス Skype for Business Server**

|**クラス**|**変更**|**クラスまたは属性**|
|:-----|:-----|:-----|
|ユーザー  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add:mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

