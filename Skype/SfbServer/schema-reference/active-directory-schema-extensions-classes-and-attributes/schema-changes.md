---
title: Skype for Business Server でのスキーマの変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。 スキーマ拡張は、Skype for Business Server で必要なクラスと属性を追加します。
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296659"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Skype for Business Server でのスキーマの変更
 
Skype for Business Server を展開して運用する前に、スキーマを拡張して Active Directory ドメインサービスを準備する必要があります。 スキーマ拡張は、Skype for Business Server で必要なクラスと属性を追加します。

> [!NOTE]
> Lync Server 2013 から Skype for Business Server 2015 にアップグレードする場合は、スキーマの変更は行われないため、この記事は適用されません。
  
Skype for Business Server では、いくつかの新しいクラスと属性が必要になります。また、既存のクラスと属性もいくつか変更されます。 さらに、Skype for Business Server の構成情報の多くは、以前のバージョンと同じように、AD DS ではなく中央管理ストアに保存されています。 以下の情報は、Skype for Business Server の AD DS にも保存されています。
  
- **スキーマの拡張機能**:
    
  - ユーザー オブジェクトの拡張
    
  - サポートされている以前のバージョンの Lync Server との下位互換性を維持するためのクラスの拡張機能。
    
- **データ**(Skype for Business Server 拡張スキーマと既存のスキーマクラスに保存されています):
    
  - ユーザー SIP の Uniform Resource Identifier (URI) とその他のユーザー設定
    
  - 返信グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
  - 中央管理ストアへのポインター
    
  - Kerberos 認証アカウント (オプションのコンピューターオブジェクト)
    
このトピックでは、Skype for Business Server で必要な Active Directory スキーマの変更について説明します。 以前のバージョンの Office Communications Server によって導入されたスキーマの変更については説明しません。 クラスとその説明の一覧については、「 [Skype For Business Server のスキーマクラスと説明](schema-classes-and-descriptions.md)」を参照してください。 属性とその説明の一覧については、「 [Skype For Business Server のスキーマ属性と説明](schema-attributes-and-descriptions.md)」を参照してください。 属性が含まれるクラスの一覧については、「 [Skype For Business Server のクラス別のスキーマ属性](schema-attributes-by-class.md)」を参照してください。
  
Msrtcsip-userenabled true プレフィックスは、Skype for Business Server に固有のクラスと属性を識別します。
  
## <a name="new-active-directory-attributes"></a>新しい Active Directory の属性

次の表では、Skype for Business Server によって追加される Active Directory の属性について説明します。
  
**Skype for Business Server によって追加された属性**

|**属性**|**説明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |このマルチバリュー属性は、ユーザーに適用される保留ポリシーの識別子を保持します。 保留ポリシーは、保留中のユーザーのメールボックスアイテムを保持します。 この属性は Exchange 2013 と共有されます。  <br/> |
|Msrtcsip-userenabled true-UserRoutingGroupId  <br/> |これは、SIP ルーティンググループの ID です。 同じグループ内のユーザーは、同じフロントエンドサーバーに登録されます。  <br/> |
|Msrtcsip-userenabled true-MirrorBackEndServer  <br/> |この属性は、フロントエンドプールによって使用されるミラー化された SQL Server バックエンドを格納するために使用されます。  <br/> |
   
## <a name="modified-active-directory-classes"></a>変更された Active Directory クラス

次の表では、Skype for Business Server によって変更される Active Directory クラスについて説明します。
  
**Skype for Business Server によって変更されたクラス**

|**クラス**|**変更**|**Class または Attribute**|
|:-----|:-----|:-----|
|ユーザー  <br/> |追加: 指定した値を含む  <br/> 追加: 指定した値を含む  <br/> |ProxyAddresses  <br/> Msrtcsip-userenabled true-UserRoutingGroupId  <br/> |
|問い合わせ  <br/> |追加: 指定した値を含む  <br/> 追加: 指定した値を含む  <br/> |ProxyAddresses  <br/> Msrtcsip-userenabled true-UserRoutingGroupId  <br/> |
|メール受信者  <br/> |追加: 指定した値を含む  <br/> |msExchUserHoldPolicies  <br/> |
|Msrtcsip-userenabled true-GlobalTopologySetting  <br/> |追加: 指定した値を含む  <br/> |Msrtcsip-userenabled true-MirrorBackEndServer  <br/> |
   

