---
title: Microsoft Teams のクラウド ビデオ相互運用性の設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: この資料では、計画し、組織でユーザーのクラウドのビデオの相互運用機能を設定する方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b171b3fb5e73561ea5aea54e6e4f25bfabe6b0dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198863"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams のクラウド ビデオ相互運用性の設定

[ビデオの相互運用機能をクラウド取引先を選択](cloud-video-interop.md)したら、導入、プロビジョニングの詳細とパートナーのテナントのキーと、組織内のビデオの相互運用アプリケーションに同意の取得の設定を計画する必要があります。 プロセスの概要を次の図に示します。 

![CVI を組織で展開します。](media/deploying-cvi.png)

## <a name="plan"></a>計画

組織で使用するには、パートナーやパートナーを識別する方法については、[マイクロソフト チームのクラウド ビデオの相互運用機能](cloud-video-interop.md)を参照してください。 

ユーザー ベース、同時実行とサイトのさまざまな支援を計画します。 

- 使用する配置モデルとホストされているモデルを選択します。
- 組織に最適なライセンス プランを選択します。 
- Vm の容量の計画では、ビデオ ・ インフラストラクチャをホストしています。

## <a name="configure"></a>構成 

クラウド ビデオの相互運用機能を構成するのには以下の手順を実行します。 

1. (テナント キー、Appid...) を選択したがあるパートナーやパートナーから構成情報を取得します。 組織の 1 つまたは複数のビデオ相互運用パートナーを使用することができます。 

2. ネットワークが正しく構成されていることを確認します。 境界ネットワークの走査をサポートするための標準に準拠したビデオ ファイアウォールを構成します。 次に例を示します。 
    - Cisco の VCS-e                  
    - ポリコム RPAD

3. Exchange と OTD に統合された会議室を構成します。 ほとんどの場合、その他のリレーを設定する必要がありますで環境内で構成されています。


## <a name="provision"></a>準備
 
テナントとなるパートナー サービスにダイヤルアウトします。 次の例では、813878896@t.plcm.vc は、テナントのキーです。 

![テナントの例](media/tenant-key-example.png) 

テナントのキー、およびビデオの相互運用機能の座標を使用して会議を作成するには、[ユーザーまたは組織全体にも有効にすることは、次のコマンドレットを実行する必要があります。

 
- ** [Get CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** マイクロソフトでは、サポートされているパートナーのクラウドのビデオの相互運用機能を使用する取引先を指定するための事前に構築されたポリシーを提供します。

    このコマンドレットを使用すると、組織内で使用できる事前に構築されたポリシーを識別できます。 1 つ以上の補助金 CsTeamsVideoInteropServicePolicy コマンドレットを活用すること、ユーザーにこのポリシーを割り当てることができます。
 
- **[与える CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** 許可 CsTeamsVideoInteropServicePolicy コマンドレットを使用すると、組織で使用するため事前に構築されたポリシーを割り当てたり、特定のユーザーにポリシーを割り当てることができます。
 
- **[新しいの CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** 新規の CsVideoInteropServiceProvider を使用すると、組織が使用にはサポートされている CVI パートナーに関する情報を指定します。
 
- **[セット CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** セット-CsVideoInteropServiceProvider を使用して、組織で使用して、サポートされている CVI パートナーに関する情報を更新します。
 
- ** [Get CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** 組織内で使用するには、すべての構成されているプロバイダーを取得します。
 
- **[削除 CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** 削除 CsVideoInteropServiceProvider を使用すると、組織が不要になった使用するプロバイダーのすべてのプロバイダー情報を削除します。  
 
## <a name="consent"></a>同意するものと

ビデオ会議デバイス パートナー サービスを経由して、組織の会議に参加するには、(VTCs) のアクセス許可の承認を提供する必要があります。 この同意のリンクもパートナーによって提供されます。  
 
次の手順が完了すると、テナントが有効な場合に、Grant コマンドレット、または組織内のユーザーのすべてを使用して個別に有効にするユーザーはこれらのスケジュールを設定するすべてのチーム会議で VTC の座標があります。 VTC は、その座標を使用してこれらの会議に参加できます。


|名前|アプリケーションのアクセス許可の概要| 説明|
|--|--|---|
|Calls.JoinGroupCall.All|アプリ (プレビュー) とグループ通話や会議に参加します。|サインインしているユーザーに、組織のグループの呼び出しとスケジュールされたミーティングに参加するようにアプリケーションを使用できます。  アプリケーションは、テナント内の会議ディレクトリ ユーザーの特権を使用して結合されます。|
|Calls.JoinGroupCallasGuest.All|(プレビュー) ゲスト ユーザーとグループの通話や会議に参加します。|匿名でログインしているユーザーに、組織のグループ呼び出しおよび予約されたミーティングに参加するようにアプリケーションを使用できます。  アプリケーションは、テナント内の会議にゲストとして参加できます。|
|Calls.AccessMedia.All|アプリ (プレビュー) としての呼び出しでアクセスのメディア ストリーム|呼び出し、サインインしているユーザーがいない状態でメディア ストリームへの直接アクセスを取得するアプリケーションを使用できます。|
|OnlineMeetings.Read.All|読み取りオンライン会議の詳細 (プレビュー)|サインイン中のユーザー、組織内のオンライン会議の詳細を参照するようにアプリケーションを使用できます。|

## <a name="schedule"></a>スケジュール

次に、ビデオの相互運用機能の座標を使用してチームの会議のスケジュールを設定します。 有効なユーザーを使用してチームのミーティングをスケジュールできます。
- [アドインを Outlook の会議のチーム](teams-add-in-for-outlook.md)
- チームのクライアント デスクトップ コンピューターとモバイル


## <a name="join"></a>Join

VTC のデバイスでチームの会議を結合するには次のようにします。
 
- IVR (インタラクティブ音声応答)
    - Tenantkey@domain を使用してパートナーの IVR にダイヤルインすることができます。 
    - IVR のパートナーが表示されたらは、VTC の conferenceId、チーム会議に接続し、先の入力が求められます。
- 直通ダイヤル
    - Tenantkey の完全な文字列を使用して直接ダイヤル機能を使用して、パートナーの IVR と対話するのには、チームの会議に直接ダイヤルできます。VTC ConferenceId@domain。
- ワンタッチ ダイヤル
    - 統合のチームの部屋を使っている場合は、(せずにすべてのダイヤル文字列を入力する必要がある)、パートナーによって提供されているワンタッチ ダイヤル機能を使用できます。

最後に、オーディオ、ビデオ、およびコンテンツの共有を使用して、ミーティングでチームのユーザーと連携します。 