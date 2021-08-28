---
title: Grant-CsSetupPermissionで行Skype for Business Server
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
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: セットアップを委任するには、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサル グループにアクセス許可を付与し、その OU 内の RTCUniversalServerAdmins グループのメンバーが、ドメイン管理者グループのメンバーでなくても、指定されたドメインに Skype for Business Server をインストールできます。
ms.openlocfilehash: 160882e70ba1126765adf7f73f6c6a15fb25bf2b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613883"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Grant-CsSetupPermissionで行Skype for Business Server
 
セットアップを委任するには、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサル グループにアクセス許可を付与し、その OU 内の RTCUniversalServerAdmins グループのメンバーが、ドメイン管理者グループのメンバーでなくても、指定されたドメインに Skype for Business Server をインストールできます。 
  
**Grant-CsSetupPermission** コマンドレットは、次の表で指定されているように、RTCUniversalServerAdmins グループに OU に対するアクセス許可を付与します。
  
**OU 内のオブジェクトに対して付与されるアクセス許可**

|**アクセス許可の適用先:**|**付与されるアクセス許可:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特別なアクセス権: <br/>  servicePrincipalName の読み込み <br/>  servicePrincipalName の書き込み <br/>  ツリーの削除 <br/>  ディレクトリ変更のレプリケート <br/> |
|子の serviceConnectionPoint オブジェクト  <br/> | 特別なアクセス権: <br/>  アクセス許可の読み取り <br/>  アクセス許可の書き込み <br/>  子の作成 <br/>  子の削除 <br/>  内容の一覧表示 <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子の msRTCSIP-Server オブジェクト  <br/> | 特別なアクセス権: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子の msRTCSIP-WebComponents オブジェクト  <br/> | 特別なアクセス権: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子の msRTCSIP-MCU オブジェクト  <br/> | 特別なアクセス権: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子の msRTCSIP-MediationServer オブジェクト  <br/> | 特別なアクセス権: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子の msRTCSIP-ApplicationServer オブジェクト  <br/> | 特別なアクセス権: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子の msRTCSIP-ConnectionPoint オブジェクト  <br/> | 特別なアクセス権: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子のコンピューター オブジェクト  <br/> | serviceConnectionPoint に対する特別なアクセス: <br/>  子オブジェクトの作成 <br/>  子オブジェクトの削除 <br/>  ツリーの削除 <br/>  パブリック情報に対する特別なアクセス: <br/>  プロパティの読み取り <br/>  DNS ホスト名に対する特別なアクセス: <br/>  プロパティの読み取り <br/> |
   

