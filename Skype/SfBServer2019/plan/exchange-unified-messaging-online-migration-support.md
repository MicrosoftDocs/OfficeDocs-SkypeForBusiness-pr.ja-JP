---
title: Exchange ユニファイド メッセージングの移行サポート
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft は、2020 年 2 月 28 日Exchangeユニファイド メッセージング オンライン (ExchUMO) サービスを廃止します。 この記事では、影響を受けるお客様がビジネス継続性を計画するために知り、何を行う必要があるのかを要約します。
ms.openlocfilehash: 933ba625506496c01242b26712e9b6d5b020dbb199c5f515444f7a8734fb84b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279595"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange ユニファイド メッセージングの移行サポート

> [!IMPORTANT]
> **2020 年 2 月 28 Exchange Online太平洋時間午後 5 時現在、ユニファイド メッセージング サービスはサポートされていません。すべてのボイスメール アカウントは、Microsoft クラウド ボイスメールサービスに移行されています。残りの自動応答トラフィックは監視され、いつでも中断される可能性があります。**

2019 年 2 月 8 日の発表を参照して、Microsoft は 2020 年 2 月 28 日までに Exchange ユニファイド メッセージング オンライン (ExchUMO) サービスを廃止します。 [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) この記事では、影響を受けるお客様がビジネスの継続性を計画するために知り、計画する必要がある内容の概要を示します。

ExchUMO は、ボイスメール、自動応答、通話キュー、FAX 統合サービス用に顧客によって展開されます。 Microsoft は、お客様がオンラインおよびオンライン サービス電話システム数千人の顧客をサポートしているサービスへの移行を支援Skype for Business計画Microsoft Teams。

ボイスメールは主に Microsoft による移行です。管理者の関与や投資は、顧客のサブセットに必要になる場合があります。 自動応答は管理者による移行です。クラウド クラウド サービスで既存の ExchUMO 自動応答ツリーを自動応答する必要があります。 サードパーティ PBX で ExchUMO 機能を使用しているお客様は、サードパーティの PBX システムをサポートしていないため、Skype クラウド サービスに移行されません。 このブログでは、サード パーティサポートの退職計画[](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)が発表されました。この展開モデルのお客様は、Microsoft のユニファイド コミュニケーション プラットフォーム/サービスの 1 つにユーザーを移行したり、これらのユーザー用のサード パーティのボイスメールや自動応答ソリューションを取得することができます。 FAX 統合はクラウドベースのサービスではサポートされていません。お客様はサードパーティ のソリューションに移行する必要があります。

## <a name="who-is-affected"></a>Who影響を受ける場合

ユニファイド メッセージング オンライン サービスから次の機能Exchangeお客様が影響を受ける可能性があります。

- ボイスメール サービス
- 自動応答 サービス
- 通話キュー サービス
- FAX 統合

> [!Note]
> ユニファイド メッセージングを使用してオンプレミスExchange Serverを使用しているお客様は影響を受け取る必要があります。

ユーザー エクスペリエンスへの影響におけるユーザーエクスペリエンスと管理者エクスペリエンスの影響 [について詳しくは、以下をご覧ください](#user-experience-impact)。

## <a name="migration-plan-overview"></a>移行計画の概要

Microsoft は、ExchUMO から機能を使用しているさまざまな顧客展開を特定し、次の計画に基づいて顧客の移行を支援します。

|顧客グループ |タイムライン  |詳細  |
|---------|---------|---------|
|移行の準備ができているお客様<br><br>移行する機能:<br><ul><li>ボイスメール</ul>   |   2019 年 3 月 ~ 5 月  |例:<ul><li>    簡単なボイスメールの展開と使用方法をお持ちのお客様<li>移行を実行するために Microsoft のすべての要件が確立されているお客様<ul>|
|前提条件をお持ちのお客様<br><br>移行する機能:<br><ul><li>ボイスメール<li>自動応答<li>通話キュー</ul> |  2019 年 5 月 ~ 12 月 |例: <br><ul><li>ハイブリッド構成が完了していない<li>ハイブリッド PSTN 番号が設定されていない</ul>|
|顧客への投資に対して管理者&必要な顧客<br><br>移行する機能:<ul><li>voicemail<li>自動応答<li>通話キュー<li>FAX 統合</ul>| 2020 年 2 月まで  | 例: <br><ul><li>ExchUMO サービスはサード パーティ製 PBX によって使用されます<li>PSTN サブスクライバー アクセス要件をお持ちのお客様<li>SFB 2010 のお客様 (サポートされていません)<li>FAX 統合</ul> |

## <a name="voicemail-migration-guidelines"></a>ボイスメール移行のガイドライン

### <a name="get-informed"></a>情報を取得する

ユーザーのスムーズな移行 [を](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 計画するには、ブログのお知らせとこの記事を理解してください。 ボイス[メール機能Skype for Business詳細については](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)、「ボイスメールとオプションの確認」を電話システムしてください。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>ハイブリッド トポロジSkype for Business確立する

ハイブリッド トポロジが確立Skype for Business場合は、ボイスメール ユーザーのスムーズな移行を有効にする必要があります。 詳細については[、「configure Skype for Business ハイブリッド](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)」を参照してください。

> [!Note]
> ボイスメール サービスの移行のためにオンラインでユーザーを移行する必要はない。 ただし、オンプレミスのユーザーがボイスメール サービス電話システムを利用するには、ハイブリッド トポロジを確立する必要があります。

### <a name="plan-your-auto-attendant-migration"></a>自動応答の移行を計画する

管理者は、いつでも ExchUMO からクラウド自動応答への自動応答の移行を開始できます。 詳細については [、「クラウド自動応答のセットアップ](/microsoftteams/create-a-phone-system-auto-attendant) 」を参照してください。

Microsoft は、移行に必要と考える可能性がある追加の自動応答機能を引き続き提供しています。 管理者は、機能セットを評価し、自動応答インスタンスを必要に応じて移行する必要があります。 機能一覧の比較については [、「ExchUMO](#exchumo-and-azure-cloud-based-services-feature-matrix)と Azure クラウドベースのサービス機能マトリックス」を参照してください。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>ボイスメールの移行後の検証とテストを計画する

ボイスメールの移行は Microsoft によって駆動されます。 前提条件のハイブリッド トポロジが確立されている場合、管理者は何もする必要はありません。 Microsoft は、必要な検証とテストを実行して、ユーザーのボイスメールの移行が中断されないか確認します。 管理者は、自分の側でテストと検証を実行してください。 推奨 [されるテスト 計画については、「推奨される](#suggested-test-plan-and-post-migration-validation-for-admins) テスト 計画と移行後の検証」を参照してください。

> [!Note]
> Lync Server 2010 はサポートされていません。 2010 サーバー展開の場合は、サーバーのアップグレードを計画するか、ユーザーをサーバーに移行Microsoft Teams。  

### <a name="monitor-the-admin-notification-center"></a>管理通知センターの監視

管理者通知センターで、ユーザーの移行に関する詳細とタイムラインに関する通知を確認します。 移行期間の少なくとも 30 日前に通知が送信されます。

> [!Note]
> ユーザーの移行タイムラインで通知を受け取り、ビジネス上重要な理由で移行を延期する場合は、Microsoft サポートに連絡してください。 2020 年 2 月 28 日の退職日を超えて移行を延期することはできません。 その他の質問がある場合は、アカウント チームまたは Microsoft サポートにお問い合わせください。 既にサポート Microsoft 365またはOffice 365を使用しているお客様は、サポート ケースを使用してMicrosoft 365 管理センター。

### <a name="consider-opting-in-for-a-planned-migration"></a>計画された移行をオプトインすることを検討する

予定されているボイスメール サービスの CVM への移行をオプトインできます。 オプトインする前に、この記事の詳細、特に次のセクションを確認してください。

- 移行手順 (このセクション)
- ExchUMO および Azure クラウドベースのサービス機能マトリックス
- ユーザー エクスペリエンスへの影響

管理された移行を選択すると、移行前の 30 日間の通知が管理者ポータル メッセージ センター Microsoft 365されません。

計画された移行をオプトインするには、管理者の電子メール アドレスから次の情報を[](mailto:cvm@microsoft.com)cvm@microsoft.com メール要求を送信します。

- 優先日 (火曜日): 移行ウェーブは毎週火曜日に実行されます。 2019 年 12 月 3 日を超えない火曜日の日付を選択してください。
 
- テナント ID: この形式の 32 文字の番号 0046728c-688a-4472-a38f-098fec60ac6x。 テナント ID は、Azure 管理ポータルの Microsoft 365 Azure AD、または次の PowerShell コマンドレットを使用して確認できます。`Get-CsTenant | Select ObjectId`

テナントが正常に移行されると、確認メールが届きます。

## <a name="auto-attendant-migration-guidelines"></a>自動応答の移行ガイドライン

Microsoft 365 および Office 365 組織の管理者は、Microsoft Cloud 自動応答 サービスで Exchange UM Online 自動応答を再作成し、2020 年 2 月 28 日の Exchange UMO サービスの退職日より前に、そのユーザーにオンプレミスの電話番号を切り替える必要があります。 これは、新しいクラウド自動応答を正常に移行してテストするために推奨されるガイドラインです。 自動応答が多数の場合は[、Exchange UM](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)自動応答 から Cloud 自動応答 移行スクリプトを使用して、自動応答の一括移行を簡略化できます。

### <a name="auto-attendant-setup"></a>Auto attendantのセットアップ

直前の問題を回避し、Cloud 自動応答 サービスの機能とエクスペリエンスを理解するために、新しい自動応答のセットアップを早期に開始してください。 1 つ以上のギャップ機能を必要とする自動応答の場合は、展開の準備にギャップ機能が利用可能な場合に自動応答を作成してテストできます。 ギャップ機能の詳細については、「付録」を [参照してください](#appendix)。

1. [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant)を使用Exchange UMO コマンドレットを使用して既存の自動応答の構成をエクスポートします。  
2. PowerShell[の Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt)コマンドレットをExchange Online、案内応答メディア ファイルをエクスポートし (使用する場合)、そのファイルを別の形式.mp3します。
3. 「クラウド自動応答を[](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)計画する」および「クラウド[](/microsoftteams/create-a-phone-system-auto-attendant)自動応答を設定する」の手順に従って、管理者センターまたは Powershell を使用して自動応答Microsoft Teams作成します。
4. メニュー オプションが変更された場合は、案内応答を確認します。
5. この記事の「既知の問題」の「自動応答 PSTN への通話転送」回避策を使用[](#known-issues)して、応答グループへの転送を構成します。  
6. 新しい自動応答を内部的に呼び出すか、テスト電話番号を割り当て、テストします。  

### <a name="cutover"></a>一括

1. 電話番号を UMO 自動応答Exchange新しい自動応答に切り替えます。
2. SIP URI を連絡先オブジェクトからリソース アカウントに移動します。
3. 新しく割り当てられた電話番号を使用して、自動応答をテストして検証します。

## <a name="appendix"></a>付録

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO および Azure クラウドベースのサービス機能マトリックス

| サービス | 機能レベル | 特徴 | 備考  | クラウド VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | サービス機能| サードパーティ PBX のサポート    | UM Online からの SIP 通知メッセージを使用した MWI (メッセージ待機インジケーター) などのサード パーティ製 PBX に提供Exchange含む | N   | Y    |
| VM | サービス機能  | サポート Skype for Business Server   |  | Y | Y    |
| VM | サービス機能 | サポート Microsoft Teams|  | Y | N    |
| VM | サービス機能 | 電子情報開示と保持  | セキュリティとコンプライアンスの場合  | Y | Y    |
| VM | サービス機能 | Exchangeルールのサポート | セキュリティとコンプライアンスの場合  | Y | Y    |
| VM | ユーザー機能 | PSTN ダイヤルイン アクセス  | サブスクライバー アクセス  | N | Y    |
| VM | ユーザー機能 | 代理人  | 通話メールの受信が見つからない  | N | Y    |
| VM | ユーザー機能 | PSTN Outlook 音声アクセス   | サブスクライバー アクセス  | N | Y    |
| VM | ユーザー機能 | 認証されたエンドポイントを使用したダイヤルイン | ボイス メール サービスを呼び出して音声メッセージをリッスンし、ボイスメール設定を変更する| Y | Y    |
| VM | ユーザー機能 | ボイスメールを無効にするユーザー設定   |  | Y | Y    |
| VM | ユーザー機能 | 個人用案内応答を変更するユーザー設定  |  | Y | Y    |
| VM | ユーザー機能 | OOF 案内応答を作成するユーザー設定  |  | Y | Y    |
| VM | ユーザー機能 | 既定の言語を変更するユーザー設定  |  | Y | Y    |
| VM | ユーザー機能 | TTS で既定の案内応答を上書きするユーザー設定  |  | Y | N    |
| VM | ユーザー機能 | 個人の案内応答を記録する (認証されたデバイス) |  | Y | Y    |
| VM | ユーザー機能 | 個人用案内応答 (PSTN) を録音する - 電話で再生する |  | N | Y    |
| VM | ユーザー機能 | 文字起こしを無効にするユーザー設定 |  | N | Y    |
| VM | ユーザー機能 | 文字起こし  |  | Y | Y    |
| VM | ユーザー機能 | SIP 通知メッセージを使用した MWI (メッセージ待機インジケーター) |  | N | Y    |
| VM | ユーザー機能 | MP3 オーディオ ファイル形式 (Outlook    |  | Y | Y    |
| VM | ユーザー機能 | 可変速度の再生制御 |  | Y | Y    |
| VM | ユーザー機能 | ボイスメールの転送  | 受信したボイスメールを他のユーザーに転送する | Y | Y    |
| VM | ユーザー機能 | ユーザーのグループに音声メッセージを送信する  |ボイスメールブロードキャスト   | N | Y   |
| VM | ユーザー機能 | SMS を使用したボイスメール通知    | ユーザーが新しいボイスメールを持っているときに SMS を受信できる    | N | Y    |
| VM | ユーザー機能 | サポートされている案内応答言語 | 詳細はこちら: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| VM | ユーザー機能 | 通話応答ルール |  | Y | Y    |
| VM | ユーザー機能 | 電話で再生する (PSTN)- メッセージを再生する | 自分のセルに電話して音声メッセージを聞く  | N | Y    |
| VM | ユーザー機能 | 電話で再生する (Auth)- メッセージを再生する | 認証済みデバイスで電話する  | N | Y    |
| VM | ユーザー機能 | 複数のユーザー間の共有メールボックス |  | Y | Y    |
| VM | 発信者の機能  | 発信者エクスペリエンス - 保護されたボイスメール | 発信者は、記録されたメッセージを保護済みとしてマークするオプションを選択できます| N | Y    |
| VM | 発信者の機能  | 発信者エクスペリエンス - プライベートボイスメール | 発信者は、録音されたメッセージをプライベートとしてマークするオプションを選択できます  | N | Y    |
| VM | 発信者の機能  | 無音検出   |  | N | Y    |
| VM | Tenant-Admin機能 | サーバーレベルで保護されたボイスメール    | テナント管理者は、受信ボイスメールを保護済みとしてマークするサービス レベルのルールを構成できます | Y | Y    |
| VM | Tenant-Admin機能 | 記録期間の制限時間の変更  |     | Y | Y    |
| VM | Tenant-Admin機能 | 変更無音検出タイムアウト    |  | 該当なし    | Y    |
| VM | Tenant-Admin機能 | 入力エラーの数を変更する | CVM: 3 にハード コード | N | Y    |
| VM | Tenant-Admin機能 | 既定の言語を変更する |  | Y | Y    |
| VM | Tenant-Admin機能 | 文字起こしを無効または有効にする |  | Y | Y    |
| VM | Tenant-Admin機能 | 通話中の通知を無効または有効にする |  | N | Y    |
| VM | Tenant-Admin機能 | Microsoft がボイス メール のプレビューを改善する    |  | Y | Y    |
| VM | Tenant-Admin機能 | 有効なユーザーのテキスト メッセージをカスタマイズする|  | 該当なし    | Y    |
| VM | Tenant-Admin機能 | トランスクリプションの不適切なマスキング|  | Y | N    |
| VM | Tenant-Admin機能 | ボイスメール ポリシー    |   | Y | Y    |
| VM | Tenant-Admin機能 | Web ポータルの管理   |  | CY19   | Y    |
| VM | Tenant-Admin機能 | PowerShell   |  | Y | Y    |
| UM | ユーザー機能 | 認定電話のメッセージ待機インジケーター (MWI) Skype for Business表示   |電話パートナーから提供される場合  | いいえ | はい    |
| AA | サービス機能 | AA サポート 3rd-party PBX    |  | N | Y    |
| AA | サービス機能 | サポート Skype for Business Server   |  | Y | Y    |
| AA | サービス機能 | サポート Microsoft Teams|  | Y | N    |
| AA | サービス機能 | 名前によるダイヤル、DTMF 入力    |  | Y | Y    |
| AA | サービス機能 | 名前によるダイヤル、音声入力  |  | Y | Y    |
| AA | サービス機能 | 多言語サポート | ここでの言語の詳細: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | サービス機能 | 演算子、CQ、またはユーザーへの転送 |  | Y | Y    |
| AA | サービス機能 | PSTN 番号への内部転送 (DID RNL)  |  | Y | Y    |
| AA | サービス機能 | PSTN 番号への外部転送  |  | 以下の「既知の問題」セクションを参照してください。 | Y    |
| AA | サービス機能 | 勤務時間 |  | Y | Y    |
| AA | サービス機能 | メニュー オプション | IVR メニュー オプション  | Y | Y    |
| AA | サービス機能 | クラウド PSTN 番号を AA に割り当てる |  | Y | N    |
| AA | サービス機能 | AA へのプレム PSTN 番号の割り当て  |  | Y | Y    |
| AA | サービス機能 | ユーザーのカスタム選択  | 組織のユーザーのカスタマイズされたリストに発信者がアクセスできる| Y | Y    |
| AA | サービス機能 | 時間外および休日の処理  |  | Y | Y    |
| AA | サービス機能 | テキストから音声へのカスタム案内応答  |  | Y | Y    |
| AA | サービス機能 | 内線ダイヤル   | 内線番号をダイヤルしてユーザーにアクセスする  | Y   | Y    |
| AA | サービス機能 | AA 発信者がメッセージを残すメールボックス    |  | Y   | Y    |
| AA | サービス機能 | AA への複数の PSTN 番号の割り当て|  | Y | Y    |
| AA | Tenant-Admin機能 | Web ポータルの管理   |  | Y | N    |
| AA | Tenant-Admin機能 | PowerShell コマンドレット  |  | Y | Y    |
| FAX| サービス機能 | FAX 統合|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>管理者に推奨されるテスト計画と移行後の検証

ユーザーが クラウド ボイスメール に移行されたと確認するには、ボイスメールをユーザーに任せ、メッセージ本文を確認Outlook。 クラウド ボイスメールには、次のフッターがあります。

"トランスクリプションを使用してありがとうございます! 上記のトランスクリプトが表示されない場合は、音質が文字起こしに十分明確ではなかったからです。

ユーザーの移行後にボイスメール機能をテストする場合は、次のシナリオを検討してください。

- アプリや IP 電話など、組織内のすべてのエンドポイントの種類にわたるボイスメール アクセスを検証します。
- 構成済みのパーソナライズされた案内応答が発信者に再生されていることをサンプル ユーザーと検証します。
- 組織にユーザーの文字起こしを無効にする法的要件またはコンプライアンス要件がある場合は、移行後に無効になっている必要があります。 詳細については、「Set [up クラウド ボイスメール」 を参照してください](/microsoftteams/set-up-phone-system-voicemail)。
- 以前に VM ポリシーとルールExchange構成済みの場合は、有効な設定を行います。
- ユーザー設定を変更する クラウド ボイスメール PowerShell コマンドレットについて理解してください。  

### <a name="user-experience-impact"></a>ユーザー エクスペリエンスへの影響

次に、エンド ユーザーのボイスメール移行エクスペリエンスの概要を示します。


|エクスペリエンス  |ユーザー エクスペリエンスの変更|
|---------|---------|
|メール通知 | 変更なし<br>ボイスメール アカウントのライセンス認証/移行についてユーザーに通知する電子メールは送信されません。 |
|以前のメッセージへのアクセス | 変更なし<br>ユーザーは、サポートされているすべてのエンドポイントで以前のボイスメール メッセージにアクセスできます。 |
|Outlook で VM を受信する、SFB Apps| 変更なし<br>ユーザーは引き続き、サポートされているすべてのエンドポイントでボイスメール メッセージを受信します。 |
|文字起こし | 拡張<br>CVM の文字起こしの精度は ExchUMO よりはるかに高く、サポートされている言語です。 |
|ユーザー設定 | 新しいエクスペリエンス<br>ユーザーは、ユーザー設定ポータル (USP) からユーザー設定を変更できます。 ユーザーは、ボイスメールメールのハイパーリンク、または SFB クライアントの [User-Settings] ボタンから USP にアクセスできます。 https://aka.ms/vmsettings.
 |機能| 詳細については、機能セットの比較を参照してください。 |
|Outlookのルール | 変更なし<br>以前に作成したルールは、移行後の CVM メッセージに適用されます。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM でのユーザー管理とプロビジョニング

新しいSkype for Businessユーザーは、作成時にクラウド ボイスメール用に自動的にプロビジョニングされます。 新しいボイスメール ユーザーをプロビジョニングするために、管理者の作業またはライセンスを追加する必要はありません。 既存[および新規ユーザークラウド ボイスメール](/microsoftteams/set-up-phone-system-voicemail)ポリシー管理の詳細については、「Set up クラウド ボイスメール」を参照してください。

### <a name="admin-auto-attendant-management-experience"></a>管理者自動応答管理エクスペリエンス

自動応答の詳細については、「クラウド自動応答のセットアップ [」を参照してください](/microsoftteams/create-a-phone-system-auto-attendant)。

### <a name="known-issues"></a>既知の問題

#### <a name="greeting-inconsistencies"></a>案内応答の不整合

すべてのユーザーがテナントに移行された後でも、サービスが完全に終了するまで、サブスクライバー アクセスはテナントで引き続き機能クラウド ボイスメール。 ユーザーの混乱と一貫性のないエクスペリエンスを回避するには、移行後に案内応答が変更された後にサブスクライバー アクセスを無効にします。 これを行うには、を使用して各サブスクライバー アクセス回線の EXUM 連絡先を削除します `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自動応答 PSTN への通話転送

Skype for Business Server または Skype for Business Server の応答グループ サービス (RGS) を介して外部 PSTN 電話番号に自動応答通話を転送するには、PSTN 電話番号または RGS 電話番号に設定された通話転送を持つ新しいオンプレミス ユーザーを作成します。 ユーザーがユーザーに対して有効にされ、正しく構成エンタープライズ VoIP音声ポリシーが割り当てられている必要があります。

#### <a name="shared-mailbox-is-still-accessible"></a>共有メールボックスに引き続きアクセス可能

UM Online を使用して構成Exchange共有メールボックスは、CVM への移行後も引き続きメッセージを受信し、ユーザーはユーザーにアクセスOutlook。 ただし、これらのメールボックスの案内応答メッセージを変更するアクセスは、CVM に移行した後は使用できません。 自動応答の発信者をキャプチャするために使用される共有メールボックスをお持ちのお客様は、リリース後に自動応答機能と通話キュー共有メールボックス機能を利用する必要があります (ETA 2019 年 10 月)。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>"ユーザー名がユーザー名を使用Skype for Business" バナーが表示される

CVM サービスは Microsoft Teams インフラストラクチャに基づいており、Skype for Business クライアントからの呼び出しによって、クライアントに情報バナーが表示され、「ユーザー名は Skype for Business を使用していない。 より充実したエクスペリエンスを得る場合は、会議に切り替Teams会議を開始Skypeしてください。
このバナーが表示されないSkype for Business、ユーザーのクライアントを最新の C2R クライアント更新プログラムに更新してください。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"ボイス メールのセットアップ" で OWA にアクセスする

クライアントから **[ボイス** メールの設定] をクリックすると、CVM への移行後、Skype for Business Server 2015/2013 のお客様は引き続き Office Web Access (OWA) ポータル ページに移動します。 OWA の [ボイスメール] タブからすべての設定が削除され、バナーにリダイレクト リンクが表示され、ユーザーが CVM ユーザー設定ポータルに移動します。

#### <a name="changing-greeting-remotely"></a>リモートで案内応答を変更する

PSTN サブスクライバー アクセスは CVM ではサポートされていません。 リモートで案内応答を変更する必要があるユーザーの場合は、モバイル クライアントのボイスメール IVR サービスに"案内応答の変更" メニュー オプションが追加されました。 ユーザーは、モバイル クライアントダイヤルパッドの "1" キーを押し続け、このサービスを呼び出します。