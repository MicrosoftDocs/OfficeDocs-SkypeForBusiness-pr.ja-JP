---
title: 'Lync Server 2013: VideoStream テーブル'
TOCTitle: VideoStream テーブル
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48271910
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の VideoStream テーブル

 

_**トピックの最終更新日:** 2015-03-09_

1 つのレコードが 1 つのビデオ ストリームを表します。通常、1 つのビデオ メディア ラインに 2 つのビデオ ストリームが含まれます。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>メディア ライン内の一意の ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部、プライマリ</p></td>
<td><p>ペイロードの説明。詳細については、「<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ セッション時の最大ネットワーク ジッター。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 統計情報に基づく往復時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ ストリームの最大往復時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal(5.4)</p></td>
<td><p> </p></td>
<td><p>通話時の平均パケット損失率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal(5.4)</p></td>
<td><p> </p></td>
<td><p>通話時に観測された最大パケット損失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ ストリームの帯域幅の推定。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char(9)</p></td>
<td><p> </p></td>
<td><p>幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ ストリームの平均ビット レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal(9.4)</p></td>
<td><p> </p></td>
<td><p>ビデオの受信フレーム レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal(9.4)</p></td>
<td><p> </p></td>
<td><p>ビデオの送信フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ セッション時の最大ビデオ ビット レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>decimal(9.4)</p></td>
<td><p> </p></td>
<td><p>失われた合計ビデオ フレーム数の割合。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>該当なし。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>decimal(9.4)</p></td>
<td><p></p></td>
<td><p>失われた合計ビデオ フレーム数の割合。</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Common Interchange Format (CIF) 解像度を使用した通話のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>VGA 解像度を使用した通話のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>HD720 解像度を使用した通話のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>フレームが欠落していない通話時間のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>B フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>BP フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>BPSP フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>BPSPI フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>受信側のストリーム データが受信されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>送信側のストリーム データが受信されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</p>
<p>0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>呼び出しが損失輻輳状態にあった時間の割合を示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>ネットワーク パケットの遅延到着により輻輳が発生している間に行われた呼び出しの割合を示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>呼び出しがネットワーク リソースを奪い合っていた時間の割合を示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>呼び出し中に測定された最小推定帯域幅。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>呼び出し中に測定された最大推定帯域幅。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>呼び出し中に測定された推定帯域幅の標準偏差。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>呼び出し中に測定された平均推定帯域幅。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>ネットワーク接続がマルチビュー ビデオをサポートできなかったとエンドポイントによって判断された通話のパーセンテージ。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>一方向のバーストの合計発生数。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>一方向のバーストの合計密度。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向のバーストの合計期間。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>一方向のギャップの合計発生数。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向のギャップの合計密度。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向のギャップの合計期間。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>decimal(9.4)</p></td>
<td><p></p></td>
<td><p>ビデオ パケットが失われたレート。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>ビデオに割り当てる平均帯域幅。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部</p></td>
<td><p>送信者が使用するビデオ コーデックの種類。詳細については、「<a href="lync-server-2013-codecdescription-table.md">CodecDescription テーブル</a>」を参照してください。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者が使用する解像度の幅。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者が使用する解像度の高さ。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者が使用する平均ビデオ フレーム レート伝送。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者の最大ビット レート。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者の平均ビット レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者が使用するビデオ ストリームの最大数。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部</p></td>
<td><p>受信者が使用するビデオ コーデック。詳細については、「<a href="lync-server-2013-codecdescription-table.md">CodecDescription テーブル</a>」を参照してください。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>受信者が使用する解像度の幅。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>受信者が使用する解像度の高さ。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>受信者が使用する平均ビデオ フレーム レート。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>受信者の最大ビット レート。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>受信者の平均ビット レート。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>受信者の最大ビデオ ストリーム。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>受信者の最小ビデオ ストリーム。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>受信者のビデオ モード (ギャラリー、単一ストリームなど)。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>前方向エラー訂正の適用後のパケット損失レート。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>動的機能フラグがアクティブだった時間の割合。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char(9)</p></td>
<td><p></p></td>
<td><p>呼び出し中に測定された最小解像度。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>低ビット レートのしきい値を下回る通話のパーセンテージ (70 キロビット/秒)。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>低フレーム レートのしきい値を下回る通話のパーセンテージ (7.5 フレーム/秒、受信)。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>最小解像度で発生した通話のパーセンテージ。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>通話の長さ (秒単位)。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>データが複数の通話から収集されたかどうかを示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

