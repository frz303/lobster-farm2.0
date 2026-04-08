	<!DOCTYPE html>
	<html lang="zh-CN">
	<head>
	    <meta charset="UTF-8">
	    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	    <title>龙虾养殖管理系统</title>
	    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
	    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
	    <style>
	        body { background-color: #f3f4f6; }
	        .nav-active { background-color: #0d9488; color: white; }
	        .fade-enter-active, .fade-leave-active { transition: opacity 0.3s ease; }
	        .fade-enter-from, .fade-leave-to { opacity: 0; }
	    </style>
	</head>
	<body>
	<div id="app" class="min-h-screen flex flex-col">
	    <!-- 顶部导航 -->
	    <nav class="bg-teal-800 text-white p-4 shadow-md flex justify-between items-center">
	        <h1 class="text-xl font-bold tracking-wider">🦞 龙虾养殖管理系统</h1>
	        <div class="flex space-x-2">
	            <button @click="currentTab='dashboard'" :class="currentTab==='dashboard' ? 'bg-teal-600' : 'hover:bg-teal-700'" class="px-3 py-1 rounded transition">首页概览</button>
	            <button @click="currentTab='pond'" :class="currentTab==='pond' ? 'bg-teal-600' : 'hover:bg-teal-700'" class="px-3 py-1 rounded transition">地块管理</button>
	            <button @click="currentTab='feed'" :class="currentTab==='feed' ? 'bg-teal-600' : 'hover:bg-teal-700'" class="px-3 py-1 rounded transition">饲料投放</button>
	            <button @click="currentTab='hydrology'" :class="currentTab==='hydrology' ? 'bg-teal-600' : 'hover:bg-teal-700'" class="px-3 py-1 rounded transition">水文资料</button>
	            <button @click="currentTab='finance'" :class="currentTab==='finance' ? 'bg-teal-600' : 'hover:bg-teal-700'" class="px-3 py-1 rounded transition">收支管理</button>
	            <button @click="currentTab='settings'" :class="currentTab==='settings' ? 'bg-teal-600' : 'hover:bg-teal-700'" class="px-3 py-1 rounded transition">系统设置</button>
	        </div>
	    </nav>
	    <main class="flex-1 p-6 overflow-auto">
	        <!-- 首页概览 -->
	        <div v-if="currentTab==='dashboard'" class="grid grid-cols-1 md:grid-cols-4 gap-6">
	            <div class="bg-white p-6 rounded-lg shadow-sm border-l-4 border-teal-500">
	                <h2 class="text-gray-500 text-sm">养殖地块</h2>
	                <p class="text-3xl font-bold text-teal-700">{{ ponds.length }} 块</p>
	            </div>
	            <div class="bg-white p-6 rounded-lg shadow-sm border-l-4 border-blue-500">
	                <h2 class="text-gray-500 text-sm">累计收入</h2>
	                <p class="text-3xl font-bold text-blue-700">¥ {{ totalIncome.toFixed(2) }}</p>
	            </div>
	            <div class="bg-white p-6 rounded-lg shadow-sm border-l-4 border-red-500">
	                <h2 class="text-gray-500 text-sm">累计支出</h2>
	                <p class="text-3xl font-bold text-red-700">¥ {{ totalCost.toFixed(2) }}</p>
	            </div>
	            <div class="bg-white p-6 rounded-lg shadow-sm border-l-4 border-green-500">
	                <h2 class="text-gray-500 text-sm">净收益</h2>
	                <p class="text-3xl font-bold" :class="totalIncome - totalCost >= 0 ? 'text-green-700' : 'text-red-700'">¥ {{ (totalIncome - totalCost).toFixed(2) }}</p>
	            </div>
	        </div>
	        <!-- 通用列表与表单模板 -->
	        <div v-else class="bg-white p-6 rounded-lg shadow-sm">
	            <div class="flex justify-between items-center mb-6">
	                <h2 class="text-2xl font-bold text-gray-800">{{ titles[currentTab] }}</h2>
	                <button @click="openModal(null)" class="bg-teal-600 hover:bg-teal-700 text-white px-4 py-2 rounded shadow transition">+ 新增记录</button>
	            </div>
	            <div class="overflow-x-auto">
	                <table class="min-w-full bg-white border">
	                    <thead>
	                        <tr class="bg-gray-100 text-left text-sm text-gray-600">
	                            <th class="py-3 px-4 border-b" v-for="field in fields[currentTab]" :key="field.key">{{ field.label }}</th>
	                            <th class="py-3 px-4 border-b text-center">操作</th>
	                        </tr>
	                    </thead>
	                    <tbody>
	                        <tr v-if="currentData.length === 0"><td :colspan="fields[currentTab].length + 1" class="py-4 text-center text-gray-400">暂无数据</td></tr>
	                        <tr v-for="(item, index) in currentData" :key="item.id" class="hover:bg-gray-50 border-b text-sm">
	                            <td class="py-3 px-4" v-for="field in fields[currentTab]" :key="field.key">
	                                <span v-if="field.key === 'pondId'">{{ getPondName(item[field.key]) }}</span>
	                                <span v-else-if="field.type === 'date'">{{ item[field.key] }}</span>
	                                <span v-else-if="field.key === 'amount' || field.key === 'price'">¥ {{ Number(item[field.key]).toFixed(2) }}</span>
	                                <span v-else>{{ item[field.key] }}</span>
	                            </td>
	                            <td class="py-3 px-4 text-center">
	                                <button @click="openModal(item)" class="text-blue-500 hover:text-blue-700 mr-2">编辑</button>
	                                <button @click="deleteItem(item.id)" class="text-red-500 hover:text-red-700">删除</button>
	                            </td>
	                        </tr>
	                    </tbody>
	                </table>
	            </div>
	        </div>
	        <!-- 系统设置页 -->
	        <div v-if="currentTab==='settings'" class="bg-white p-6 rounded-lg shadow-sm mt-6">
	            <h2 class="text-xl font-bold mb-4">数据管理</h2>
	            <p class="text-gray-600 mb-4 text-sm">由于系统使用浏览器本地存储，请定期导出备份数据，以免清除浏览器缓存时丢失。更换设备或浏览器时，可导入恢复。</p>
	            <div class="flex space-x-4">
	                <button @click="exportData" class="bg-green-600 hover:bg-green-700 text-white px-4 py-2 rounded shadow">导出备份</button>
	                <label class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded shadow cursor-pointer">
	                    导入恢复
	                    <input type="file" @change="importData" class="hidden" accept=".json">
	                </label>
	            </div>
	        </div>
	    </main>
	    <!-- 弹窗表单 -->
	    <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
	        <div class="bg-white rounded-lg shadow-xl w-full max-w-lg p-6 relative">
	            <button @click="showModal = false" class="absolute top-3 right-3 text-gray-500 hover:text-gray-700 text-xl font-bold">&times;</button>
	            <h3 class="text-xl font-bold mb-4">{{ modalTitle }}</h3>
	            <div class="space-y-4">
	                <div v-for="field in fields[currentTab]" :key="field.key">
	                    <label class="block text-sm font-medium text-gray-700 mb-1">{{ field.label }}</label>
	                    <select v-if="field.type === 'select'" v-model="formData[field.key]" class="w-full border-gray-300 rounded-md shadow-sm border p-2 focus:ring-teal-500 focus:border-teal-500">
	                        <option value="">请选择</option>
	                        <option v-for="pond in ponds" :key="pond.id" :value="pond.id">{{ pond.name }}</option>
	                    </select>
	                    <input v-else :type="field.type || 'text'" v-model="formData[field.key]" class="w-full border-gray-300 rounded-md shadow-sm border p-2 focus:ring-teal-500 focus:border-teal-500">
	                </div>
	            </div>
	            <div class="mt-6 flex justify-end space-x-3">
	                <button @click="showModal = false" class="px-4 py-2 bg-gray-200 text-gray-700 rounded hover:bg-gray-300">取消</button>
	                <button @click="saveItem" class="px-4 py-2 bg-teal-600 text-white rounded hover:bg-teal-700">保存</button>
	            </div>
	        </div>
	    </div>
	</div>
	<script>
	const { createApp, ref, computed, watch, onMounted } = Vue;
	createApp({
	    setup() {
	        const currentTab = ref('dashboard');
	        const showModal = ref(false);
	        const formData = ref({});
	        // 数据源
	        const ponds = ref([]);
	        const feedRecords = ref([]);
	        const hydrologyRecords = ref([]);
	        const financeRecords = ref([]);
	        // 字段配置
	        const titles = {
	            pond: '地块管理',
	            feed: '饲料投放记录',
	            hydrology: '水文资料管理',
	            finance: '收支管理'
	        };
	        const fields = {
	            pond: [
	                { key: 'name', label: '地块/塘口名称' },
	                { key: 'area', label: '面积(亩)', type: 'number' },
	                { key: 'status', label: '状态(如: 养殖中/空塘/清淤)' }
	            ],
	            feed: [
	                { key: 'date', label: '投放日期', type: 'date' },
	                { key: 'pondId', label: '地块', type: 'select' },
	                { key: 'feedType', label: '饲料类型' },
	                { key: 'quantity', label: '投放量(kg)', type: 'number' },
	                { key: 'notes', label: '备注' }
	            ],
	            hydrology: [
	                { key: 'date', label: '监测日期', type: 'date' },
	                { key: 'pondId', label: '地块', type: 'select' },
	                { key: 'ph', label: 'pH值', type: 'number' },
	                { key: 'oxygen', label: '溶解氧', type: 'number' },
	                { key: 'ammonia', label: '氨氮', type: 'number' },
	                { key: 'temp', label: '水温(℃)', type: 'number' }
	            ],
	            finance: [
	                { key: 'date', label: '日期', type: 'date' },
	                { key: 'type', label: '类型(收入/支出)' },
	                { key: 'category', label: '分类(虾苗/饲料/租金/卖虾等)' },
	                { key: 'amount', label: '金额(元)', type: 'number' },
	                { key: 'notes', label: '备注' }
	            ]
	        };
	        const currentData = computed(() => {
	            switch(currentTab.value) {
	                case 'pond': return ponds.value;
	                case 'feed': return feedRecords.value;
	                case 'hydrology': return hydrologyRecords.value;
	                case 'finance': return financeRecords.value;
	                default: return [];
	            }
	        });
	        const modalTitle = computed(() => {
	            const prefix = formData.value.id ? '编辑' : '新增';
	            return prefix + (titles[currentTab.value] || '');
	        });
	        // 财务统计
	        const totalIncome = computed(() => financeRecords.value.filter(f => f.type === '收入').reduce((sum, f) => sum + Number(f.amount || 0), 0));
	        const totalCost = computed(() => financeRecords.value.filter(f => f.type === '支出').reduce((sum, f) => sum + Number(f.amount || 0), 0));
	        const getPondName = (pondId) => {
	            const pond = ponds.value.find(p => p.id === pondId);
	            return pond ? pond.name : '未知地块';
	        };
	        const openModal = (item) => {
	            if (item) {
	                formData.value = { ...item };
	            } else {
	                const initForm = {};
	                fields[currentTab.value].forEach(f => initForm[f.key] = '');
	                formData.value = initForm;
	            }
	            showModal.value = true;
	        };
	        const saveItem = () => {
	            const tab = currentTab.value;
	            let dataArr;
	            switch(tab) {
	                case 'pond': dataArr = ponds; break;
	                case 'feed': dataArr = feedRecords; break;
	                case 'hydrology': dataArr = hydrologyRecords; break;
	                case 'finance': dataArr = financeRecords; break;
	            }
	            if (formData.value.id) {
	                const index = dataArr.value.findIndex(d => d.id === formData.value.id);
	                if (index !== -1) dataArr.value[index] = { ...formData.value };
	            } else {
	                formData.value.id = Date.now().toString();
	                dataArr.value.push({ ...formData.value });
	            }
	            showModal.value = false;
	            saveToLocal();
	        };
	        const deleteItem = (id) => {
	            if (!confirm('确定要删除这条记录吗？')) return;
	            const tab = currentTab.value;
	            switch(tab) {
	                case 'pond': ponds.value = ponds.value.filter(d => d.id !== id); break;
	                case 'feed': feedRecords.value = feedRecords.value.filter(d => d.id !== id); break;
	                case 'hydrology': hydrologyRecords.value = hydrologyRecords.value.filter(d => d.id !== id); break;
	                case 'finance': financeRecords.value = financeRecords.value.filter(d => d.id !== id); break;
	            }
	            saveToLocal();
	        };
	        // 本地存储操作
	        const saveToLocal = () => {
	            const data = {
	                ponds: ponds.value,
	                feedRecords: feedRecords.value,
	                hydrologyRecords: hydrologyRecords.value,
	                financeRecords: financeRecords.value
	            };
	            localStorage.setItem('lobsterFarmData', JSON.stringify(data));
	        };
	        const loadFromLocal = () => {
	            const saved = localStorage.getItem('lobsterFarmData');
	            if (saved) {
	                const data = JSON.parse(saved);
	                ponds.value = data.ponds || [];
	                feedRecords.value = data.feedRecords || [];
	                hydrologyRecords.value = data.hydrologyRecords || [];
	                financeRecords.value = data.financeRecords || [];
	            }
	        };
	        // 导入导出
	        const exportData = () => {
	            const data = localStorage.getItem('lobsterFarmData');
	            const blob = new Blob([data], { type: "application/json" });
	            const url = URL.createObjectURL(blob);
	            const a = document.createElement('a');
	            a.href = url;
	            a.download = `龙虾养殖数据备份_${new Date().toISOString().slice(0,10)}.json`;
	            a.click();
	            URL.revokeObjectURL(url);
	        };
	        const importData = (event) => {
	            const file = event.target.files[0];
	            if (!file) return;
	            const reader = new FileReader();
	            reader.onload = (e) => {
	                try {
	                    const data = JSON.parse(e.target.result);
	                    if (data.ponds) {
	                        localStorage.setItem('lobsterFarmData', JSON.stringify(data));
	                        loadFromLocal();
	                        alert('数据导入成功！');
	                    } else {
	                        alert('无效的备份文件！');
	                    }
	                } catch (error) {
	                    alert('文件解析失败！');
	                }
	            };
	            reader.readAsText(file);
	        };
	        onMounted(() => {
	            loadFromLocal();
	        });
	        return {
	            currentTab, showModal, formData, ponds, feedRecords, hydrologyRecords, financeRecords,
	            titles, fields, currentData, modalTitle, totalIncome, totalCost,
	            getPondName, openModal, saveItem, deleteItem, exportData, importData
	        };
	    }
	}).mount('#app');
	</script>
	</body>
	</html>
