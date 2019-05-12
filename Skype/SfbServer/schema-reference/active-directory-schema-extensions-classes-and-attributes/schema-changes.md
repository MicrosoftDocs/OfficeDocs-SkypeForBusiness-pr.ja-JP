---
title: Skype ビジネス サーバーのスキーマの変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 展開して、ビジネス サーバー、Skype で運用する前にスキーマを拡張することによって Active Directory ドメイン サービスを準備する必要があります。 スキーマの拡張機能は、Skype でビジネスのサーバーのために必要な属性とクラスを追加します。
ms.openlocfilehash: 5b6c3f036b1bc194331c721ea2d45564f0827d1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924844"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Skype ビジネス サーバーのスキーマの変更
 
展開して、ビジネス サーバー、Skype で運用する前にスキーマを拡張することによって Active Directory ドメイン サービスを準備する必要があります。 スキーマの拡張機能は、Skype でビジネスのサーバーのために必要な属性とクラスを追加します。

> [!NOTE]
> アップグレードする Lync Server 2013 に Skype ビジネス サーバー 2015 の場合、は、スキーマの変更は行われませんし、この資料は適用されませんのでします。
  
Skype ビジネス サーバーのでは、いくつかの新しいクラスと属性が必要ですし、いくつかの既存のクラスおよび属性を変更します。 さらに、ビジネス サーバーの Skype の多くの構成情報は以前のバージョンのように AD DS ではなく中央管理ストアに格納されます。 次の情報はまだ Skype で AD DS のビジネス サーバーの格納されます。
  
- **スキーマの拡張機能**:
    
  - ユーザー オブジェクトの拡張
    
  - Lync Server のサポートされている以前のバージョンとの下位互換性を維持するためにクラスを拡張します。
    
- **データ**(ビジネス サーバー拡張スキーマの Skype では既存のスキーマ クラスに格納されます。)
    
  - ユーザー SIP 統一リソース識別子 (URI) およびその他のユーザー設定
    
  - 応答グループや会議アテンダントなどのアプリケーションの連絡先オブジェクト
    
  - 中央管理ストアへのポインター
    
  - Kerberos 認証アカウント (オプションのコンピューター オブジェクト)
    
このトピックでは、Skype で必要なビジネス サーバー、Active Directory スキーマの変更について説明します。 Office Communications Server の以前のバージョンで導入されたスキーマの変更については説明しません。 クラスとその説明のリストは、[スキーマのクラスおよびビジネス サーバーの Skype での説明](schema-classes-and-descriptions.md)を参照してください。 属性とその説明のリストは、[スキーマの属性および Skype ビジネス サーバーの説明](schema-attributes-and-descriptions.md)を参照してください。 属性を持つクラスのリストが含まれている、 [Skype のビジネス サーバーのクラスによってスキーマの属性](schema-attributes-by-class.md)を参照してください、可能性があります。
  
MsRTCSIP プレフィックスは、クラスとは、Skype のビジネス サーバーに固有の属性を識別します。
  
## <a name="new-active-directory-attributes"></a>新規の Active Directory 属性

次の表では、Skype でビジネスのサーバーに追加される Active Directory の属性について説明します。
  
**Skype ビジネス サーバーの追加の属性**

|**属性**|**説明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |この複数値属性を保持するの識別子は、ユーザーに適用されるポリシーを保持します。 ポリシーがユーザーのメールボックス アイテムを保持する保留リストの中に保持します。 この属性は、Exchange 2013 で共有されています。  <br/> |
|msRTCSIP UserRoutingGroupId  <br/> |これは、SIP のルーティング グループの id。 同じグループ内のユーザーは、同じフロント エンド サーバーに登録されます。  <br/> |
|msRTCSIP MirrorBackEndServer  <br/> |この属性を使用して、フロント エンド プールによって使用されるミラー化された SQL Server のバックエンドを格納します。  <br/> |
   
## <a name="modified-active-directory-classes"></a>変更された Active Directory クラス

次の表では、Skype でビジネスのサーバーの変更を Active Directory クラスについて説明します。
  
**Skype ビジネス サーバーの変更クラス**

|**クラス**|**変更**|**クラスまたは属性**|
|:-----|:-----|:-----|
|ユーザー  <br/> |追加: は  <br/> 追加: は  <br/> |ProxyAddresses  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|連絡先  <br/> |追加: は  <br/> 追加: は  <br/> |ProxyAddresses  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|メール受信者  <br/> |追加: は  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |追加: は  <br/> |msRTCSIP MirrorBackEndServer  <br/> |
   

