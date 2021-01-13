---
title: 常設チャット コンプライアンス SQL Server ストアの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 常設チャット サーバーまたはSQL Server機能のデータベースを提供するストアのコンプライアンス 構成を構成します。
ms.openlocfilehash: 1f931df0135e857b53a8067b114e3f9f438c614c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818697"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>常設チャット コンプライアンス SQL Server ストアの追加
 
常設チャット サーバーまたは常設SQL Serverのコンプライアンス機能のデータベースを提供するストアのコンプライアンス 構成を行います。
  
 **SQL Serverストア**: 既存のチャット をSQL Server、必要に応じて常設チャットのインスタンスを選択します。
  
[ **新規]** をクリックして、新しいSQL Serverし、必要に応じて常設チャット コンプライアンス データの新しいインスタンスを定義します。
  
常設チャット **コンプライアンス SQL Server** ミラー化されたデータベースを提供する SQL Server データベースとオプションのインスタンスを構成するには、[ストア ミラーリングを有効にする] チェック ボックスをオンにします。
  
リストから選択し **、SQL Server** 常設チャット コンプライアンス SQL Serverのミラーとして機能する SQL Server インスタンスとオプションのインスタンスを格納SQL Server。
  
[ **新規]** をクリックして、新しいSQL Serverし、必要に応じて、常設チャット の新しいインスタンスをSQL Serverします。
  
[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] の一覧で、フェールオーバーのシナリオにおいて監視サーバーとして機能する SQL Server を選択します。 ミラーリング監視サーバーは、常設チャット サーバーのデータをミラー化またはホストしませんが、ミラー化された構成内の 1 つの SQL Server だけがアクティブな SQL Server 状態になります。
  
[ **新規]** をクリックして、ミラーリング監視SQL Server常設チャット コンプライアンス監視のインスタンスを定義SQL Server定義します。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
この **プール** のバックアップ サーバーのオプションの入力が終了したら、[次へ] をクリックしてSQL Server、常設チャット サーバー プールの定義に進みます。
  
すべての変更を破棄して **新しい常設チャット プールの定義** ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 での常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Skype for Business Server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成](../../manage/persistent-chat/configure-compliance.md)
