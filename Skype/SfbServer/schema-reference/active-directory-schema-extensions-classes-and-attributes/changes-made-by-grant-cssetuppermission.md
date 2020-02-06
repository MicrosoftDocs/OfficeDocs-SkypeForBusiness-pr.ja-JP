---
title: Skype for Business Server で付与されたアクセス許可によって行われる変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: セットアップを委任するには、特定の Active Directory 組織単位 (OU) に対して RTCUniversalServerAdmins ユニバーサルグループへのアクセス許可を付与し、その OU の RTCUniversalServerAdmins グループのメンバーが、Skype for Business Server をインストールできるようにするDomain Admins グループのメンバーになっていない指定のドメイン。
ms.openlocfilehash: 844cfa586523750b804564482146c0e76b39fc38
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815515"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Skype for Business Server で付与されたアクセス許可によって行われる変更
 
セットアップを委任するには、特定の Active Directory 組織単位 (OU) に対して RTCUniversalServerAdmins ユニバーサルグループへのアクセス許可を付与し、その OU の RTCUniversalServerAdmins グループのメンバーが、Skype for Business Server をインストールできるようにするDomain Admins グループのメンバーになっていない指定のドメイン。 
  
**グラント setuppermissions**コマンドレットは、次の表で指定されているように、OU に対して RTCUniversalServerAdmins group アクセス許可を付与します。
  
**OU 内のオブジェクトに付与されているアクセス許可**

|**権限の対象:**|**付与されるアクセス許可:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊なアクセス: <br/>  ServicePrincipalName を読み上げる <br/>  ServicePrincipalName の書き込み <br/>  ツリーの削除 <br/>  ディレクトリの変更の複製 <br/> |
|子孫の serviceConnectionPoint オブジェクト  <br/> | 特殊なアクセス: <br/>  読み取りアクセス許可 <br/>  書き込み権限 <br/>  子の作成 <br/>  子の削除 <br/>  リストの内容 <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|下位の Msrtcsip-userenabled true オブジェクト  <br/> | 特殊なアクセス: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|下位の Msrtcsip-userenabled true-WebComponents オブジェクト  <br/> | 特殊なアクセス: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子孫の Msrtcsip-userenabled true-MCU オブジェクト  <br/> | 特殊なアクセス: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子孫の Msrtcsip-userenabled true-MediationServer オブジェクト  <br/> | 特殊なアクセス: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子 Msrtcsip-userenabled true ApplicationServer オブジェクト  <br/> | 特殊なアクセス: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子 Msrtcsip-userenabled true ConnectionPoint オブジェクト  <br/> | 特殊なアクセス: <br/>  プロパティの書き込み <br/>  プロパティの読み取り <br/>  ツリーの削除 <br/> |
|子コンピューターオブジェクト  <br/> | ServiceConnectionPoint の特殊なアクセス: <br/>  子オブジェクトを作成する <br/>  子オブジェクトを削除する <br/>  ツリーの削除 <br/>  パブリック情報への特別なアクセス: <br/>  プロパティの読み取り <br/>  DNS ホスト名の特殊なアクセス: <br/>  プロパティの読み取り <br/> |
   

