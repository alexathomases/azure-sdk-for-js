## API Report File for "@azure-rest/health-deidentification"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { AbortSignalLike } from '@azure/abort-controller';
import { CancelOnProgress } from '@azure/core-lro';
import { Client } from '@azure-rest/core-client';
import { ClientOptions } from '@azure-rest/core-client';
import { CreateHttpPollerOptions } from '@azure/core-lro';
import { ErrorModel } from '@azure-rest/core-client';
import { ErrorResponse } from '@azure-rest/core-client';
import { HttpResponse } from '@azure-rest/core-client';
import { OperationState } from '@azure/core-lro';
import { Paged } from '@azure/core-paging';
import { PagedAsyncIterableIterator } from '@azure/core-paging';
import { PathUncheckedResponse } from '@azure-rest/core-client';
import { RawHttpHeaders } from '@azure/core-rest-pipeline';
import { RawHttpHeadersInput } from '@azure/core-rest-pipeline';
import { RequestParameters } from '@azure-rest/core-client';
import { StreamableMethod } from '@azure-rest/core-client';
import { TokenCredential } from '@azure/core-auth';

// @public (undocumented)
export interface CancelJob {
    post(options?: CancelJobParameters): StreamableMethod<CancelJob200Response | CancelJobDefaultResponse>;
}

// @public (undocumented)
export interface CancelJob200Headers {
    "x-ms-client-request-id"?: string;
}

// @public
export interface CancelJob200Response extends HttpResponse {
    // (undocumented)
    body: DeidentificationJobOutput;
    // (undocumented)
    headers: RawHttpHeaders & CancelJob200Headers;
    // (undocumented)
    status: "200";
}

// @public (undocumented)
export interface CancelJobDefaultHeaders {
    "x-ms-error-code"?: string;
}

// @public (undocumented)
export interface CancelJobDefaultResponse extends HttpResponse {
    // (undocumented)
    body: ErrorResponse;
    // (undocumented)
    headers: RawHttpHeaders & CancelJobDefaultHeaders;
    // (undocumented)
    status: string;
}

// @public (undocumented)
export interface CancelJobHeaderParam {
    // (undocumented)
    headers?: RawHttpHeadersInput & CancelJobHeaders;
}

// @public (undocumented)
export interface CancelJobHeaders {
    "x-ms-client-request-id"?: string;
}

// @public (undocumented)
export type CancelJobParameters = CancelJobHeaderParam & RequestParameters;

// @public
function createClient(endpointParam: string, credentials: TokenCredential, { apiVersion, ...options }?: DeidentificationClientOptions): DeidentificationClient;
export default createClient;

// @public
export interface CustomizationOptions {
    redactionFormat?: string;
    surrogateLocale?: string;
}

// @public (undocumented)
export type DeidentificationClient = Client & {
    path: Routes;
};

// @public
export interface DeidentificationClientOptions extends ClientOptions {
    apiVersion?: string;
}

// @public
export interface DeidentificationContent {
    customizations?: CustomizationOptions;
    inputText: string;
    operation?: OperationType;
}

// @public
export interface DeidentificationJob {
    customizations?: JobCustomizationOptions;
    operation?: OperationType;
    sourceLocation: SourceStorageLocation;
    targetLocation: TargetStorageLocation;
}

// @public
export interface DeidentificationJobOutput {
    readonly createdAt: string;
    customizations?: JobCustomizationOptionsOutput;
    readonly error?: ErrorModel;
    readonly lastUpdatedAt: string;
    readonly name: string;
    operation?: OperationTypeOutput;
    sourceLocation: SourceStorageLocationOutput;
    readonly startedAt?: string;
    readonly status: JobStatusOutput;
    readonly summary?: JobSummaryOutput;
    targetLocation: TargetStorageLocationOutput;
}

// @public
export interface DeidentificationResultOutput {
    outputText?: string;
    taggerResult?: PhiTaggerResultOutput;
}

// @public (undocumented)
export interface DeidentifyDocuments200Headers {
    "operation-location": string;
    "x-ms-client-request-id"?: string;
}

// @public
export interface DeidentifyDocuments200Response extends HttpResponse {
    // (undocumented)
    body: DeidentificationJobOutput;
    // (undocumented)
    headers: RawHttpHeaders & DeidentifyDocuments200Headers;
    // (undocumented)
    status: "200";
}

// @public (undocumented)
export interface DeidentifyDocuments201Headers {
    "operation-location": string;
    "x-ms-client-request-id"?: string;
}

// @public
export interface DeidentifyDocuments201Response extends HttpResponse {
    // (undocumented)
    body: DeidentificationJobOutput;
    // (undocumented)
    headers: RawHttpHeaders & DeidentifyDocuments201Headers;
    // (undocumented)
    status: "201";
}

// @public (undocumented)
export interface DeidentifyDocumentsBodyParam {
    body: DeidentificationJob;
}

// @public (undocumented)
export interface DeidentifyDocumentsDefaultHeaders {
    "x-ms-error-code"?: string;
}

// @public (undocumented)
export interface DeidentifyDocumentsDefaultResponse extends HttpResponse {
    // (undocumented)
    body: ErrorResponse;
    // (undocumented)
    headers: RawHttpHeaders & DeidentifyDocumentsDefaultHeaders;
    // (undocumented)
    status: string;
}

// @public (undocumented)
export interface DeidentifyDocumentsHeaderParam {
    // (undocumented)
    headers?: RawHttpHeadersInput & DeidentifyDocumentsHeaders;
}

// @public (undocumented)
export interface DeidentifyDocumentsHeaders {
    "x-ms-client-request-id"?: string;
}

// @public
export interface DeidentifyDocumentsLogicalResponse extends HttpResponse {
    // (undocumented)
    body: DeidentificationJobOutput;
    // (undocumented)
    status: "200";
}

// @public (undocumented)
export type DeidentifyDocumentsParameters = DeidentifyDocumentsHeaderParam & DeidentifyDocumentsBodyParam & RequestParameters;

// @public (undocumented)
export interface DeidentifyText {
    post(options: DeidentifyTextParameters): StreamableMethod<DeidentifyText200Response | DeidentifyTextDefaultResponse>;
}

// @public (undocumented)
export interface DeidentifyText200Headers {
    "x-ms-client-request-id"?: string;
}

// @public
export interface DeidentifyText200Response extends HttpResponse {
    // (undocumented)
    body: DeidentificationResultOutput;
    // (undocumented)
    headers: RawHttpHeaders & DeidentifyText200Headers;
    // (undocumented)
    status: "200";
}

// @public (undocumented)
export interface DeidentifyTextBodyParam {
    body: DeidentificationContent;
}

// @public (undocumented)
export interface DeidentifyTextDefaultHeaders {
    "x-ms-error-code"?: string;
}

// @public (undocumented)
export interface DeidentifyTextDefaultResponse extends HttpResponse {
    // (undocumented)
    body: ErrorResponse;
    // (undocumented)
    headers: RawHttpHeaders & DeidentifyTextDefaultHeaders;
    // (undocumented)
    status: string;
}

// @public (undocumented)
export interface DeidentifyTextHeaderParam {
    // (undocumented)
    headers?: RawHttpHeadersInput & DeidentifyTextHeaders;
}

// @public (undocumented)
export interface DeidentifyTextHeaders {
    "x-ms-client-request-id"?: string;
}

// @public (undocumented)
export type DeidentifyTextParameters = DeidentifyTextHeaderParam & DeidentifyTextBodyParam & RequestParameters;

// @public (undocumented)
export interface DeleteJob204Headers {
    "x-ms-client-request-id"?: string;
}

// @public
export interface DeleteJob204Response extends HttpResponse {
    // (undocumented)
    headers: RawHttpHeaders & DeleteJob204Headers;
    // (undocumented)
    status: "204";
}

// @public (undocumented)
export interface DeleteJobDefaultHeaders {
    "x-ms-error-code"?: string;
}

// @public (undocumented)
export interface DeleteJobDefaultResponse extends HttpResponse {
    // (undocumented)
    body: ErrorResponse;
    // (undocumented)
    headers: RawHttpHeaders & DeleteJobDefaultHeaders;
    // (undocumented)
    status: string;
}

// @public (undocumented)
export interface DeleteJobHeaderParam {
    // (undocumented)
    headers?: RawHttpHeadersInput & DeleteJobHeaders;
}

// @public (undocumented)
export interface DeleteJobHeaders {
    "x-ms-client-request-id"?: string;
}

// @public (undocumented)
export type DeleteJobParameters = DeleteJobHeaderParam & RequestParameters;

// @public
export interface DocumentDetailsOutput {
    error?: ErrorModel;
    readonly id: string;
    input: DocumentLocationOutput;
    output?: DocumentLocationOutput;
    status: OperationStateOutput;
}

// @public
export interface DocumentLocationOutput {
    readonly etag: string;
    location: string;
}

// @public
export type GetArrayType<T> = T extends Array<infer TData> ? TData : never;

// @public (undocumented)
export interface GetJob {
    delete(options?: DeleteJobParameters): StreamableMethod<DeleteJob204Response | DeleteJobDefaultResponse>;
    get(options?: GetJobParameters): StreamableMethod<GetJob200Response | GetJobDefaultResponse>;
    put(options: DeidentifyDocumentsParameters): StreamableMethod<DeidentifyDocuments200Response | DeidentifyDocuments201Response | DeidentifyDocumentsDefaultResponse>;
}

// @public (undocumented)
export interface GetJob200Headers {
    "x-ms-client-request-id"?: string;
}

// @public
export interface GetJob200Response extends HttpResponse {
    // (undocumented)
    body: DeidentificationJobOutput;
    // (undocumented)
    headers: RawHttpHeaders & GetJob200Headers;
    // (undocumented)
    status: "200";
}

// @public (undocumented)
export interface GetJobDefaultHeaders {
    "x-ms-error-code"?: string;
}

// @public (undocumented)
export interface GetJobDefaultResponse extends HttpResponse {
    // (undocumented)
    body: ErrorResponse;
    // (undocumented)
    headers: RawHttpHeaders & GetJobDefaultHeaders;
    // (undocumented)
    status: string;
}

// @public (undocumented)
export interface GetJobHeaderParam {
    // (undocumented)
    headers?: RawHttpHeadersInput & GetJobHeaders;
}

// @public (undocumented)
export interface GetJobHeaders {
    "x-ms-client-request-id"?: string;
}

// @public (undocumented)
export type GetJobParameters = GetJobHeaderParam & RequestParameters;

// @public
export function getLongRunningPoller<TResult extends DeidentifyDocumentsLogicalResponse | DeidentifyDocumentsDefaultResponse>(client: Client, initialResponse: DeidentifyDocuments200Response | DeidentifyDocuments201Response | DeidentifyDocumentsDefaultResponse, options?: CreateHttpPollerOptions<TResult, OperationState<TResult>>): Promise<SimplePollerLike<OperationState<TResult>, TResult>>;

// @public
export type GetPage<TPage> = (pageLink: string, maxPageSize?: number) => Promise<{
    page: TPage;
    nextPageLink?: string;
}>;

// @public (undocumented)
export function isUnexpected(response: GetJob200Response | GetJobDefaultResponse): response is GetJobDefaultResponse;

// @public (undocumented)
export function isUnexpected(response: DeidentifyDocuments200Response | DeidentifyDocuments201Response | DeidentifyDocumentsLogicalResponse | DeidentifyDocumentsDefaultResponse): response is DeidentifyDocumentsDefaultResponse;

// @public (undocumented)
export function isUnexpected(response: DeleteJob204Response | DeleteJobDefaultResponse): response is DeleteJobDefaultResponse;

// @public (undocumented)
export function isUnexpected(response: ListJobs200Response | ListJobsDefaultResponse): response is ListJobsDefaultResponse;

// @public (undocumented)
export function isUnexpected(response: ListJobDocuments200Response | ListJobDocumentsDefaultResponse): response is ListJobDocumentsDefaultResponse;

// @public (undocumented)
export function isUnexpected(response: CancelJob200Response | CancelJobDefaultResponse): response is CancelJobDefaultResponse;

// @public (undocumented)
export function isUnexpected(response: DeidentifyText200Response | DeidentifyTextDefaultResponse): response is DeidentifyTextDefaultResponse;

// @public
export interface JobCustomizationOptions {
    redactionFormat?: string;
    surrogateLocale?: string;
}

// @public
export interface JobCustomizationOptionsOutput {
    redactionFormat?: string;
    surrogateLocale?: string;
}

// @public
export type JobStatus = string;

// @public
export type JobStatusOutput = string;

// @public
export interface JobSummary {
    bytesProcessed: number;
    canceled: number;
    failed: number;
    successful: number;
    total: number;
}

// @public
export interface JobSummaryOutput {
    bytesProcessed: number;
    canceled: number;
    failed: number;
    successful: number;
    total: number;
}

// @public (undocumented)
export interface ListJobDocuments {
    get(options?: ListJobDocumentsParameters): StreamableMethod<ListJobDocuments200Response | ListJobDocumentsDefaultResponse>;
}

// @public
export interface ListJobDocuments200Response extends HttpResponse {
    // (undocumented)
    body: PagedDocumentDetailsOutput;
    // (undocumented)
    status: "200";
}

// @public (undocumented)
export interface ListJobDocumentsDefaultHeaders {
    "x-ms-error-code"?: string;
}

// @public (undocumented)
export interface ListJobDocumentsDefaultResponse extends HttpResponse {
    // (undocumented)
    body: ErrorResponse;
    // (undocumented)
    headers: RawHttpHeaders & ListJobDocumentsDefaultHeaders;
    // (undocumented)
    status: string;
}

// @public (undocumented)
export type ListJobDocumentsParameters = ListJobDocumentsQueryParam & RequestParameters;

// @public (undocumented)
export interface ListJobDocumentsQueryParam {
    // (undocumented)
    queryParameters?: ListJobDocumentsQueryParamProperties;
}

// @public (undocumented)
export interface ListJobDocumentsQueryParamProperties {
    continuationToken?: string;
    maxpagesize?: number;
}

// @public (undocumented)
export interface ListJobs {
    get(options?: ListJobsParameters): StreamableMethod<ListJobs200Response | ListJobsDefaultResponse>;
}

// @public (undocumented)
export interface ListJobs200Headers {
    "x-ms-client-request-id"?: string;
}

// @public
export interface ListJobs200Response extends HttpResponse {
    // (undocumented)
    body: PagedDeidentificationJobOutput;
    // (undocumented)
    headers: RawHttpHeaders & ListJobs200Headers;
    // (undocumented)
    status: "200";
}

// @public (undocumented)
export interface ListJobsDefaultHeaders {
    "x-ms-error-code"?: string;
}

// @public (undocumented)
export interface ListJobsDefaultResponse extends HttpResponse {
    // (undocumented)
    body: ErrorResponse;
    // (undocumented)
    headers: RawHttpHeaders & ListJobsDefaultHeaders;
    // (undocumented)
    status: string;
}

// @public (undocumented)
export interface ListJobsHeaderParam {
    // (undocumented)
    headers?: RawHttpHeadersInput & ListJobsHeaders;
}

// @public (undocumented)
export interface ListJobsHeaders {
    "x-ms-client-request-id"?: string;
}

// @public (undocumented)
export type ListJobsParameters = ListJobsQueryParam & ListJobsHeaderParam & RequestParameters;

// @public (undocumented)
export interface ListJobsQueryParam {
    // (undocumented)
    queryParameters?: ListJobsQueryParamProperties;
}

// @public (undocumented)
export interface ListJobsQueryParamProperties {
    continuationToken?: string;
    maxpagesize?: number;
}

// @public
export type OperationStateOutput = string;

// @public
export type OperationType = string;

// @public
export type OperationTypeOutput = string;

// @public
export type PagedDeidentificationJobOutput = Paged<DeidentificationJobOutput>;

// @public
export type PagedDocumentDetailsOutput = Paged<DocumentDetailsOutput>;

// @public
export function paginate<TResponse extends PathUncheckedResponse>(client: Client, initialResponse: TResponse, options?: PagingOptions<TResponse>): PagedAsyncIterableIterator<PaginateReturn<TResponse>>;

// @public
export type PaginateReturn<TResult> = TResult extends {
    body: {
        value?: infer TPage;
    };
} ? GetArrayType<TPage> : Array<unknown>;

// @public
export interface PagingOptions<TResponse> {
    customGetPage?: GetPage<PaginateReturn<TResponse>[]>;
}

// @public
export type PhiCategoryOutput = string;

// @public
export interface PhiEntityOutput {
    category: PhiCategoryOutput;
    confidenceScore?: number;
    length: StringIndexOutput;
    offset: StringIndexOutput;
    text?: string;
}

// @public
export interface PhiTaggerResultOutput {
    entities: Array<PhiEntityOutput>;
}

// @public (undocumented)
export interface Routes {
    (path: "/jobs/{name}", name: string): GetJob;
    (path: "/jobs"): ListJobs;
    (path: "/jobs/{jobName}/documents", jobName: string): ListJobDocuments;
    (path: "/jobs/{name}:cancel", name: string): CancelJob;
    (path: "/deid"): DeidentifyText;
}

// @public
export interface SimplePollerLike<TState extends OperationState<TResult>, TResult> {
    getOperationState(): TState;
    getResult(): TResult | undefined;
    isDone(): boolean;
    // @deprecated
    isStopped(): boolean;
    onProgress(callback: (state: TState) => void): CancelOnProgress;
    poll(options?: {
        abortSignal?: AbortSignalLike;
    }): Promise<TState>;
    pollUntilDone(pollOptions?: {
        abortSignal?: AbortSignalLike;
    }): Promise<TResult>;
    serialize(): Promise<string>;
    // @deprecated
    stopPolling(): void;
    submitted(): Promise<void>;
    // @deprecated
    toString(): string;
}

// @public
export interface SourceStorageLocation {
    extensions?: string[];
    location: string;
    prefix: string;
}

// @public
export interface SourceStorageLocationOutput {
    extensions?: string[];
    location: string;
    prefix: string;
}

// @public
export interface StringIndexOutput {
    codePoint: number;
    utf16: number;
    utf8: number;
}

// @public
export interface TargetStorageLocation {
    location: string;
    overwrite?: boolean;
    prefix: string;
}

// @public
export interface TargetStorageLocationOutput {
    location: string;
    overwrite?: boolean;
    prefix: string;
}

// (No @packageDocumentation comment for this package)

```
