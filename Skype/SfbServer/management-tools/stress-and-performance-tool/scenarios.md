---
title: ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のパフォーマンスのシナリオ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: タスクのストレスおよびパフォーマンス ツールを使用してパフォーマンスとロード テストを実行するサーバー 2015 のビジネス用の Skype を構成するのには実行する必要があります。
ms.openlocfilehash: 06ca34717080421129fc03475103b34804ef280a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901698"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のパフォーマンスのシナリオ
 
タスクのストレスおよびパフォーマンス ツールを使用してパフォーマンスとロード テストを実行するサーバー 2015 のビジネス用の Skype を構成するのには実行する必要があります。
  
実行するには、Skype のビジネス サーバー 2015 のストレスおよびパフォーマンス ツール (LyncPerfTool) ビジネス サーバー 2015 トポロジの Skype が最初に関連するシナリオを構成しなければなりません。 ビジネス サーバー 2015 の Skype では、設定されていない、または構成が正しくない、負荷シミュレーションが失敗する可能性があります。 ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype、私たちの[ツールのダウンロード](https://www.microsoft.com/download/details.aspx?id=50367)の一部として、ビジネスのサーバー管理シェル スクリプトと基本的なリソース ファイルの Skype の使用例を提供しています。 ビジネス サーバーの展開について、Skype を構成するための開始点として使用することができます。 この資料では、Windows PowerShell に示す例について説明します。
  
> [!NOTE]
> このトピックには、ビジネス サーバー 2015 の Skype を一般に構成する方法について説明することはできません、その他の計画と展開のトピックがあります。 ビジネス サーバー 2015 の Skype で Windows PowerShell の使用に関する詳細については、Skype の挿入については、ここでビジネスのサーバー管理シェルのマニュアルを参照してください。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Skype ビジネス サーバーの管理にシェル スクリプトの実行について

負荷シミュレーション用に準備することができますを使用するサンプルの PowerShell スクリプトを提供しています。 これらのスクリプトは、負荷のシミュレーションとしているために、それらをシンプルかつ寛容な型指定を入手できます。 実稼働環境に適切なことがあります。 もう一度、これらのスクリプトのサンプルは、それらを確認し、多くの場合に変更を加える、環境に関連する前に実際に使用することにする必要がありますを強調します。 最低限、予想されるが、(エージェント グループに割り当てられたエージェントを指定します) に、トポロジに関する応答サービス グループ (RSG) スクリプトを変更する必要があります。 必要はありません、実行する必要がある場合。
  
> [!CAUTION]
> 確認して、これらのサンプルを理解することに注意してください。 スクリプトを実行すると、トポロジ内の既存の設定が上書きされます。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>ストレスおよびパフォーマンス ツールのクライアント バージョンの名前

以前の既定値から設定を変更した場合にクライアントのバージョンの確認ポリシーを構成する必要があります。 このことを確認していない場合は、[クライアントのバージョンを確認するドキュメント](https://msdn.microsoft.com/en-us/vsto/jj923060)を確認してください。
  
ストレスおよびパフォーマンス ツールは、ビジネス サーバー 2015 の Skype で通信するときに、既定で次のユーザー エージェントのバージョンを使用します。
  
- LSPT/15.0.0.0 (Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールを)
    
- OCPHONE/.0.522
    
LyncPerfTool の移動性 (UCWA) のクライアント。
  
- UCWA のパフォーマンス ツールと Web 会議
    
- UCWA のパフォーマンス ツールやモバイル
    

