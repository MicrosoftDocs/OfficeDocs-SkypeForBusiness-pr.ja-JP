---
title: マイクロソフト チームの会議室の管理の概要
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: マイクロソフト チームの会議室の管理の概要です。
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012494"
---
# <a name="management-overview"></a>管理の概要 

確認して、マイクロソフト チームの会議室のシステム、ユーザーの利用可能な優れた操作を提供する操作が発生しを開発し、継続的なメンテナンスを実行することが重要です。 

## <a name="monitoring"></a>監視 

マイクロソフト チームの会議室のシステムの監視は、2 つの主要な活動で構成されます。

-  デバイス、アプリケーション、および周辺機器の監視

-  品質と信頼性の監視 (救難)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>マイクロソフト チームの会議室のデバイス、アプリケーション、および周辺機器の監視

ユーザーがマイクロソフト チームの会議室の単位を使用できることを確認するには、単位は、マイクロソフト チームの会議室アプリケーションが正しく構成されてネットワークに接続されている、および、機能の周辺機器に接続するのにする必要があります。 


マイクロソフト チームの会議室のアプリケーションと接続されている周辺機器の状態についての情報は、Windows イベント ログにマイクロソフト チーム ルーム アプリケーションによって書かれた、[ログ エントリを理解するの](azure-monitor.md#understand-the-log-entries)に記載されています。 

|**設定**|**により、**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows 探して AutoAdminLogon = (dword) 1  <br/> |起動するように、マイクロソフト チームの会議室を使用します。  <br/> |
|電源管理 -\> AC、画面をオフに 10 分後  <br/> 電源管理 -\> Ac システムをスリープ状態を配置しません。  <br/> |マイクロソフト チームの部屋に接続されている表示をオフにして、自動的にスリープを有効に  <br/> |
|net accounts /maxpwage:unlimited  <br/> またはローカル アカウントのパスワードの有効期限を無効にするのと同等のことを意味します。 これを行うには、障害が発生する Skype アカウントの期限切れのパスワードについて苦情を言ってログオンが失敗すると、最終的に。 したがってこれを設定して必要があります管理者アカウント、最終的にも期限切れにする] ボックスに、コンピューター上のすべてのローカル アカウントに影響を与えるこのこと注意してください。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)で説明します。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使用したリモート管理
<a name="RemotePS"> </a>

マイクロソフト チームの会議室のシステムを監視する Microsoft オペレーション マネージャーのスイートを使用することをお勧めします。 監視と警告の基本的なセットアップ方法については、 [Azure のモニターを使用してマイクロソフト チーム ルームの展開の管理](../../deploy/deploy-clients/azure-monitor.md)を参照してください。 

このガイドを使用すると、マイクロソフト チームの部屋にいるユニットを配置ですべての問題を識別する簡単に使用できるダッシュ ボードを作成できます。 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>判断のポイント|<ul><li>マイクロソフト チームの会議室の展開を監視する操作の管理スイートを使用することを確認します。</li><li>メール ・ アラートを使用するターゲットの配布リストを決定します。</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>品質と信頼性の監視方法を定義します。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>品質と信頼性の監視 (救難)

懸念される領域を識別し、解決に向けて、継続的なオペレーションの品質と信頼性の呼び出し、会議の品質と信頼性、トレンドを監視するのには、展開の一部としてプロシージャを監視を実装することをお勧めします。 

救難に、建物の情報をアップロードするとき簡単に建物を比較し、特定の問題を絞り込んで、建物ごとのレベルでの呼び出しの品質と信頼性の傾向を調査できます。 詳細については、 [Skype のオンライン配信のビジネスおよび運用ガイド 』 のモニター ・救難](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15)をダウンロードします。 

確認し、することと[品質の経験をレビュー ガイド](https://aka.ms/qerguide)の品質と信頼性の傾向を把握するのには、次の解決するためのアクション ・ プランの作成をお勧めします。 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>チーム ルーム OS のマイクロソフトおよびマイクロソフト チームの会議室のアプリケーションを更新

製品の更新プログラムと機能強化によるメリットを得るチーム ルーム OS のマイクロソフトおよびマイクロソフト チームの会議室のアプリケーションを更新することをお勧めします。 詳細については、[マイクロソフト チームのルームの管理](room-systems-v2-operations.md#software-updates)を参照してください。 

## <a name="windows-updates"></a>Windows の更新プログラム

マイクロソフト チームの会議室では、10 企業「IoT の Windows または Windows 10 エンタープライズ (VL) 上で実行し標準のデスクトップと同じ Windows の更新プログラムおよびオペレーティング システムのビルドを受け取ります。 詳細については、 [Windows の更新プログラムの管理](updates.md)を参照してください。


## <a name="troubleshooting"></a>トラブルシューティング

管理スイートの操作、運用チームとヘルプデスク警告が表示されます、マイクロソフト チームの会議室の問題にするために上記のセクションで説明したようのアラートを設定することをお勧めします。 [PowerShell を使用してリモート管理](room-systems-v2-operations.md#remote-management-using-powershell)では、PowerShell のリモート管理に使用できるオプションが説明されています。 周辺機器が切断されているローカルの「スマート手」かを調査し、デバイスを再接続する IT サポートに依存する必要があります。 

トラブルシューティングと管理モードの詳細については、[マイクロソフト チームのルームの管理](room-systems-v2-operations.md#admin-mode-and-device-management)を参照してください。 


## <a name="see-also"></a>関連項目

[マイクロソフト チームの会議室のヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[マイクロソフト チームの会議室のプラン](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[マイクロソフト チームの会議室を配置します。](../../deploy/deploy-clients/room-systems-v2.md)

[マイクロソフト チームの会議室のコンソールを構成します。](../../deploy/deploy-clients/console.md)

[マイクロソフト チームの会議室のコンソールの設定を XML 構成ファイルを使用してリモートで管理します。](xml-config-file.md)
