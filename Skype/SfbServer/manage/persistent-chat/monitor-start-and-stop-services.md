---
title: Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '概要: 開始、停止、およびビジネス サーバー 2015 の Skype で永続的なチャット サービスを監視する方法を説明します。'
ms.openlocfilehash: 4303d4cfc950ca7c57b7f16b31bc66e1ae711397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910355"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サービスの監視、開始、および停止
 
**の概要:** 開始、停止、およびビジネス サーバー 2015 の Skype で永続的なチャット サービスを監視する方法を説明します。
  
永続的なチャット サービスと永続的なチャットのコンプライアンス ・ サービス ビジネス サーバー トポロジの Skype の一部であることができるため監視、停止、および次のコマンドレットを使用して起動。
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |詳細 Windows サービスとして実行されているビジネス サーバー 2015 コンポーネントについて、Skype に関する情報を返します。  <br/> |
|start-CsWindowsService  <br/> |サービスを開始します。  <br/> |
|stop-CsWindowsService  <br/> |サービスを停止します。  <br/> |
   
> [!NOTE]
> 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。 

これらのコマンドレットの使用法の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。
  

