---
title: "Microsoft チームのクライアントを取得します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Web、(Windows と Mac)、デスクトップとモバイルを含む Microsoft チームで使用可能なさまざまなクライアントを使用する方法を学習 (Android、iOS、および Windows Phone など)。"
ms.openlocfilehash: c10dde0e2893bc11f1d5a01eed1c30ed37ff30a0
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="get-clients-for-microsoft-teams"></a>Microsoft チームのクライアントを取得します。 
===========================

Microsoft チームでは、クライアント (Windows と Mac) に web、デスクトップとモバイル (Android、iOS、および Windows Phone など) があります。これらのクライアントでは、すべて、インターネットに接続を必要し、オフライン モードはサポートされていません。

<a name="web-client"></a>Web クライアント 
----------------

Web クライアント ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) は、さまざまなブラウザーから使用できる、完全機能クライアントです。この時点では、web クライアントは (つまり、会議に参加して、1 対 1 の呼び出し) のリアルタイムの通信をサポートしていません。ブラウザーは、サード パーティの cookie を許可するも構成する必要があります。 

プラグインまたはダウンロードの web ブラウザーでチームを実行する必要はありません。

Web クライアント ブラウザー バージョンの検出[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)への接続を実行して、Web インターフェイスへのアクセスをブロックするには、ユーザーが、デスクトップ クライアントをダウンロードすることをお勧めし、ブラウザーがサポートされていないバージョンが検出されると、またはモバイル アプリ。

<a name="internet-browser-support"></a>インターネット ブラウザー サポート
------------------------------
チームには、次のようなインターネット ブラウザーがサポートしている: Internet Explorer 11、Microsoft Edge、最新バージョンの Chrome、Firefox の最新バージョンです。

> [!NOTE]
> Safari は現在サポートされていません。チームの新機能に関する情報については、[チームのロードマップ](http://aka.ms/TeamsRoadmap)を確認してください。チームのデスクトップ クライアントをダウンロードするのには、Safari のチームを開こうとしているユーザーが表示されます。

<a name="desktop-clients"></a>デスクトップのクライアント
------------------------

Microsoft チーム デスクトップ クライアントでは、スタンドアロン アプリケーションおよび現在 Office Pro Plus の一部ではないです。Microsoft チームは、Windows (7 以上)、32 ビットと 64 ビットの両方のバージョンと MacOS (10.10 +) の両方で使用します。

デスクトップ クライアントでは、チーム会議、グループの呼び出し元とプライベート 1 対 1 の通話に (オーディオ、ビデオ、およびコンテンツの共有) リアルタイム通信サポートを提供します。

デスクトップ クライアントのダウンロードおよび (管理者権限は、チーム クライアントを PC にインストールする必要はありませんが、Mac では必須で)、適切なローカル権限がある場合は、エンドユーザー [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)から直接してインストールされていることができます。

IT 管理者は、その優先システム センター構成マネージャー (Windows) または Casper スイート (MacOS) など、組織のコンピューターにインストール ファイルを配布する方法を選択できます。



> [!NOTE]
> これらのメカニズムを介してクライアントの分布は、Microsoft チーム クライアントの最初のインストールと今後の更新プログラムではなく、します。


#### <a name="windows"></a>Windows

Windows 版の Microsoft チームのインストールでは、32 ビットと 64 ビット アーキテクチャのダウンロード可能なインストーラーを提供します。アーキテクチャは、OS のするが、オンラインのダウンロードを既定に一致する必要があります。



> [!NOTE]
> Microsoft チームのアーキテクチャ (32 ビットと 64 ビット) では、インストールされている Office のアーキテクチャに依存しません。

Windows クライアントは、ユーザーのプロファイル内にある [AppData フォルダーに配置されます。ローカルのユーザーのプロファイルに配置するには、クライアントはせず、管理者特権の権限をインストールすることができます。Windows クライアントは、次の場所にインストールされます。

-   %appdata\\ローカル\\Microsoft\\チーム

-   %appdata\\移動\\Microsoft\\チーム

ユーザーは、初めて Microsoft チーム クライアントを使用して通話を開始するときに、通信を許可するユーザーの入力を求める Windows ファイアウォールの設定に警告がわかります。警告を終了したときにも、通話を使用するために、このメッセージを無視するようにユーザーを指示することがあります。

![Windows セキュリティの警告] ダイアログのスクリーン ショット。](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> Windows ファイアウォールの構成は、「キャンセル」を選択して、メッセージを閉じた場合でも変更されます。両方の TCP および UDP プロトコルのブロックのアクションを teams.exe の 2 つの受信の規則が作成されます。

#### <a name="mac"></a>Mac

Microsoft は、Mac os X のコンピューターの場合も攻撃力インストール ファイルを提供します。Mac クライアントをインストールするには、管理者アクセス権が必要です。Mac os X クライアントの/Applications フォルダーにインストールします。


<a name="mobile-clients"></a>モバイル クライアント
--------------

Microsoft チームのモバイル アプリは Android、iOS、および Windows Phone、およびチャット ベースでの会話に参加している、外出先でユーザーの対象としていますが、ピア ツー ピアの音声通話を許可します。モバイル アプリは、Google Play、Apple App Store では、Microsoft ストア用の関連性の高いモバイル ストアに移動します。

モバイル アプリをチームの Microsoft のサポートされているモバイル プラットフォーム、次のとおりです。

-   **Android**: 4.4 以降

-   **iOS**: 10.0 またはそれ以降

-   **Windows Phone**: Windows 10 Mobile

モバイル アプリでは、分散し、モバイル対応プラットフォームのアプリ ストアにのみ、およびは使用できない MDM (モバイル デバイス管理) ソリューションを配布するまたは側読み込まを使って更新します。


| | | |
|---------|---------|---------|
|![判断するポイントをタップします。](media/Get_clients_for_Microsoft_Teams_image4.png)      |判断するポイント         |ユーザーが自分のデバイスに適切な Microsoft チーム クライアントをインストールするを防ぐ制限はありますか。         |
|![次の手順をタップします。](media/Get_clients_for_Microsoft_Teams_image5.png)     |次のステップ         |場合は、組織では、ソフトウェアのインストールを制限、プロセスが Microsoft チームと互換性があることを確認します。注: 管理者権限はクライアント インストール済みの PC の必須ではありませんが、mac のインストールに必要な         |


  <span id="_Hlk477176062" class="anchor"></span>判断するポイントは、ユーザーが自分のデバイスに適切な Microsoft チーム クライアントをインストールするを防ぐ制限はありますか。

<a name="client-update-management"></a>クライアントの更新プログラムの管理
------------------------

クライアントは現在自動的に Microsoft チーム サービスによってで更新が必要 IT 管理者が操作しません。更新が利用可能な場合は、クライアントが自動的に更新プログラムをダウンロードし、アプリが一定時間のアイドリングときに、更新プロセスが開始します。

<a name="client-side-configurations"></a>クライアント側の構成
---------------------------

現時点では、テナント管理者、PowerShell、グループ ポリシー オブジェクトまたはレジストリを通じてクライアントを構成するのにはサポートされているオプションはありません。

<a name="notification-settings"></a>通知の設定
----------------------------

現在、オプションはクライアント側の通知の設定を構成するのには、IT 管理者向けの利用可能なはありません。すべての通知オプションは、ユーザーが設定されています。次の図では、既定のクライアントの設定について説明します。

![通知のスクリーン ショット設定します。](media/Get_clients_for_Microsoft_Teams_image6.png)
