---
title: 通話分析を使用して低品質な通話をトラブルシューティングする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Microsoft Teams や Skype for Business の通話や会議に関する問題のトラブルシューティングを行うには、デバイス、ネットワーク、接続に関わる通話分析の詳細を使用します。
ms.openlocfilehash: 71a1e1c339c502da5cbbf998c75e758f2bbe3be2
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665249"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>通話分析を使用して低品質な通話をトラブルシューティングする

通話分析を使用すると、Microsoft Teams や Skype for Business の通話や接続に関する問題をトラブルシューティングできます。 通話分析は、Microsoft 365 または Office 365 アカウントの各ユーザーが行う通話および会議のデバイス、ネットワーク、および接続性についての詳細情報を表示します。 通話分析に建物、サイト、テナント情報が追加された場合は、通話とセッションごとに表示されます。 通話分析を通して得られる情報は、ユーザーの通話や会議の品質を低下させた原因を把握するのに役立ちます。 
  
## <a name="call-analytics-permissions"></a>通話分析のアクセス許可

管理者として、通話分析のすべての機能にアクセスできます。 さらに、Azure Active Directory の役割をサポートスタッフに割り当てることができます。 通話分析の一部の情報のビューのみが必要なユーザーには、Teams コミュニケーション サポート スペシャリストの役割を割り当てます。 通話分析の完全な機能にアクセスする必要があるユーザーには、Teams コミュニケーション サポート エンジニアの役割を割り当てます。 両方のアクセス許可レベルを設定すると、Microsoft Teams 管理センターのその他の部分にアクセスできなくなります。

コミュニケーション サポート スペシャリストが、基本的な通話の品質に関する問題を解決します。 会議に関する問題は調査しません。 代わりに、関連情報を収集し、コミュニケーション サポート エンジニアにエスカレートします。 コミュニケーション サポート エンジニアは、コミュニケーション サポート スペシャリストに対して表示されない詳細な通話ログの情報を確認します。 次の表では、通話分析を利用する際に、コミュニケーション サポート スペシャリストとコミュニケーション サポート エンジニアが使用できる情報の概要を示します。

割り当てられているアクセス許可レベルによって、アクセスできる情報の種類が決まります。
  
- **Teams サービス管理者または Teams コミュニケーション管理者**: 通話分析および Microsoft Teams 管理センターのすべての情報にアクセスできます。
    
- **Teams コミュニケーション サポート スペシャリスト**: データの一部だけが表示されます。 通話のトラブルシューティングを行うことはできますが、会議に関する問題は Teams コミュニケーション サポート エンジニアに引き継がれます。 その他の Microsoft Teams 管理センターにはアクセスできません。
    
- **Teams コミュニケーション サポート エンジニア**: 通話分析のすべてのデータを表示し、通話と会議の両方の問題を解決することができます。 その他の Microsoft Teams 管理センターにはアクセスできません。
    
> [!NOTE]
> コミュニケーション サポート スペシャリストの役割は、サポート階層 1 と同等です。コミュニケーション サポート エンジニアの役割は、サポート階層 2 と同じです。

Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者の役割を使用して Teams を管理する](using-admin-roles.md)」を参照してください。 Teams コミュニケーション サポート スペシャリストおよび Teams コミュニケーション サポート エンジニアの役割の詳細については、「[通話分析を設定する](set-up-call-analytics.md#set-call-analytics-permissions)」を参照してください。 
  
アクセス許可に関してサポートが必要な場合は、Teams と Skype for Business の管理者に問い合わせてください。
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>通話分析を使用して通話品質の問題をトラブルシューティングする

1. Teams のコミュニケーション サポートまたは Teams 管理者の資格情報でサインインします。

2. Web ブラウザーで、*https://admin.teams.microsoft.com* にアクセスします。
    
3. **ダッシュボード**で、**ユーザー検索**に通話のトラブルシューティンするユーザーの名前または sip アドレスのいずれかを入力するか、[**ユーザーを表示**] を選択してユーザーのリストを表示します。
    
    ![通話分析のユーザー検索のスクリーンショット](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. リストからユーザーを選択します。

5. [**通話履歴**] を選択し、トラブルシューティングする通話または会議を選択します。  最大500レコードが返されます。
    
    ![ユーザーの通話履歴ページのスクリーンショット。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. [**詳細**] タブを選択して、通話の品質が低下したり、接続の問題が発生していることを示す黄色と赤色アイテムを探します。
    
    各通話や会議のセッションの詳細において、小さな問題は黄色で表示されます。 (たとえば、次のスクリーンショットでは、平均ジッタ、最大ジッタ、平均パケット損失率として黄色で値が指定されています)。黄色は通常の範囲外で、問題の原因になっている可能性がありますが、問題の主な原因になることはほとんどありません。 赤色の場合は重大な問題であり、このセッションの通話が低品質である主な原因の可能性があります。 
    
    ![ユーザーの通話履歴の [詳細設定] タブのスクリーンショット ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
稀に、音声セッションの品質のデータは受信されません。 多くの場合、これは通話の中断、クライアントとの接続が終了することが原因です。 このような場合、セッションの評価は**使用**できません。
  
体験品質 (QoE) データがある音声セッションについては、次の表において、セッションを**低品質**とする主な問題について説明します。
  
|**問題**|**領域**|**説明**|
|:-----|:-----|:-----|
|通話設定  <br/> |セッション  <br/> |エラー コード Ms-diag 20-29 は、設定が失敗したことを示します。 ユーザーが通話または会議に参加できませんでした。  <br/> |
|音声ネットワークよって低品質と分類された通話  <br/> |セッション  <br/> |ネットワーク品質の問題 (パケット損失、ジッタ、NMOS 劣化、RTT、隠し比率) が発生しました。 低品質な通話の分類に使用される条件の詳細については、この[Microsoft blog 記事](https://go.microsoft.com/fwlink/p/?linkid=852133)を参照してください。  <br/> |
|デバイスが機能しない  <br/> |デバイス  <br/> | デバイスが正常に機能していない。 機能していないデバイスの割合: <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   
## <a name="related-topics"></a>関連トピック
[通話分析を設定する](set-up-call-analytics.md)

[通話分析および通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
