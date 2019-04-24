---
title: Skype の許可-CsSetupPermission によるビジネス サーバーの変更
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: セットアップを委任するに割り当てることができます RTCUniversalServerAdmins のユニバーサル グループにアクセス許可を特定 Active Directory 組織単位 (OU) のビジネスのサーバーでの Skype をインストールするには、その OU 内の RTCUniversalServerAdmins グループのメンバーを有効にすると、Domain Admins グループのメンバーに指定されたドメインです。
ms.openlocfilehash: 3976cb22a947e9a9590989895cf688465c8f5ef0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213390"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Skype の許可-CsSetupPermission によるビジネス サーバーの変更
 
セットアップを委任するに割り当てることができます RTCUniversalServerAdmins のユニバーサル グループにアクセス許可を特定 Active Directory 組織単位 (OU) のビジネスのサーバーでの Skype をインストールするには、その OU 内の RTCUniversalServerAdmins グループのメンバーを有効にすると、Domain Admins グループのメンバーに指定されたドメインです。 
  
**許可 CsSetupPermission**コマンドレットには、次の表で指定されている OU に RTCUniversalServerAdmins グループのアクセス許可が付与されます。
  
**OU 内のオブジェクトに与えられるアクセス許可**

|**アクセス許可が適用されます。**|**与えられるアクセス許可は次のとおりです。**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊なアクセスを許可します。 <br/>  サービス プリンシパル名を読み取る <br/>  サービス プリンシパル名を記述します。 <br/>  ツリーを削除します。 <br/>  ディレクトリ変更をレプリケートします。 <br/> |
|子孫の serviceConnectionPoint オブジェクト  <br/> | 特殊なアクセスを許可します。 <br/>  読み取りアクセス許可 <br/>  書き込みのアクセス許可 <br/>  子を作成します。 <br/>  子を削除します。 <br/>  内容の一覧表示 <br/>  プロパティを書き込み <br/>  プロパティを読み取り <br/>  ツリーを削除します。 <br/> |
|MsRTCSIP サーバーの子オブジェクト  <br/> | 特殊なアクセスを許可します。 <br/>  プロパティを書き込み <br/>  プロパティを読み取り <br/>  ツリーを削除します。 <br/> |
|子孫の msRTCSIP web コンポーネントのオブジェクト  <br/> | 特殊なアクセスを許可します。 <br/>  プロパティを書き込み <br/>  プロパティを読み取り <br/>  ツリーを削除します。 <br/> |
|MsRTCSIP MCU の子孫オブジェクト  <br/> | 特殊なアクセスを許可します。 <br/>  プロパティを書き込み <br/>  プロパティを読み取り <br/>  ツリーを削除します。 <br/> |
|子孫の msRTCSIP MediationServer オブジェクト  <br/> | 特殊なアクセスを許可します。 <br/>  プロパティを書き込み <br/>  プロパティを読み取り <br/>  ツリーを削除します。 <br/> |
|子孫の msRTCSIP アプリケーション サーバー オブジェクト  <br/> | 特殊なアクセスを許可します。 <br/>  プロパティを書き込み <br/>  プロパティを読み取り <br/>  ツリーを削除します。 <br/> |
|子孫の msRTCSIP ConnectionPoint オブジェクト  <br/> | 特殊なアクセスを許可します。 <br/>  プロパティを書き込み <br/>  プロパティを読み取り <br/>  ツリーを削除します。 <br/> |
|コンピューター オブジェクトの子孫  <br/> | ServiceConnectionPoint の特殊なアクセスを許可します。 <br/>  子オブジェクトを作成します。 <br/>  子オブジェクトを削除します。 <br/>  ツリーを削除します。 <br/>  公開についての特殊なアクセス許可: <br/>  プロパティを読み取り <br/>  DNS ホスト名の特殊なアクセスを許可します。 <br/>  プロパティを読み取り <br/> |
   

