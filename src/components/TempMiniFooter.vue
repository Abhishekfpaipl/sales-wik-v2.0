<template>
    <div class="container mt-5">
        <div class="accordion accordion-flush" id="accordionFlushExample">
            <div class="accordion-item my-4 border-0" v-for="(link, index) in links" :key="index">
                <h2 class="accordion-header">
                    <button class="accordion-button collapsed text-capitalize fs-4 bg-light border" type="button"
                        data-bs-toggle="collapse" :data-bs-target="'#flush-collapseOne' + index" aria-expanded="false"
                        :aria-controls="'flush-collapseOne' + index">
                        <span class="text-center">
                            {{ link.name }}
                        </span>
                    </button>
                </h2>
                <div :id="'flush-collapseOne' + index" class="accordion-collapse collapse show pb-5"
                    data-bs-parent="#accordionFlushExample">
                    <div class="accordion-body d-flex flex-wrap">
                        <router-link :to="link.route + sub" v-for="(sub, subIndex) in link.sublinks" :key="subIndex"
                            class="text-decoration-none text-dark text-capitalize">
                            <span>&nbsp; {{ sub }} &nbsp;|</span>
                        </router-link>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "MiniFooter",
    data() {
        return {
            links: [
                {
                    id: 1,
                    name: "We are offering product and services",
                    sublinks: [
                        // {name: "Product", slug: "we-are-offering-product-and-services"},{name: "Services", slug: "we-are-offering-product-and-services"},
                        "Product", "Services"
                    ]
                },
                {
                    id: 2,
                    name: 'we are loved by peoples',
                    sublinks: [
                        "men", "women", "children", "mother", "father", "student", "professional", "executive", "adult", "all types of people", "athlete", "other"
                    ]
                },
                {
                    id: 3,
                    name: "We are working for Categories",
                    sublinks: [
                        'Body Massage Centres',
                        'Cinema Halls', 'Schools', 'Beauty Spas', 'Dermatologists', 'Hospitals', 'Malls',
                        'Gyms', 'Beauty Parlours', 'Estate Agents', 'Banquet Halls', 'ENT Doctors', 'Book Shops', 'Bike On Rent',
                        'Sexologist Doctors', 'Neurologists', 'Gynaecologist & Obstetrician Doctors', 'Train Ticket Booking Agents',
                        'Travel Agents', 'Paying Guest Accommodations', 'General Physician Doctors', 'Dentists', 'Orthopaedic Doctors',
                        'Chemists', 'Motor Training Schools', 'Gastroenterologists', 'Car Rental', 'Salons', 'Courier Services',
                        'Dance Classes', 'Pathology Labs', 'Taxi Services', 'Cake Shops', 'AC Repair & Services', 'Mobile Phone Dealers',
                        'Pet Shops', 'Dmart', 'Packers And Movers', 'Psychiatrists', 'Dharamshalas', 'Urologist Doctors', 'Bakeries',
                        'Bicycle Dealers', 'Coffee Shops', 'Paediatricians', 'Sonography Centres', 'Yoga Classes', 'Hostels',
                        'Cardiologists', 'Electrical Shops', 'Skin Care Clinics', 'Diagnostic Centres', 'Homeopathic Doctors',
                        'Physiotherapists', 'Photo Studios', 'Plumbers', 'Music Classes', 'Electricians', 'Sports Goods Dealers',
                        'Shoe Dealers', 'Hair Stylists', 'Gift Shops', 'Ophthalmologists', 'Car Repair & Services', 'Ayurvedic Doctors',
                        'Eye Clinics', 'Restaurants', 'Carpenters', 'Jewellery Showrooms', 'Cooks On Hire', 'Stationery Shops',
                        'Nephrologists', 'Caterers', 'Interior Designers', 'Rehabilitation Center', 'Grocery Stores', 'Banks', 'ATM',
                        '5 Star Hotels', 'Hotels', 'Resorts', 'Plastic Surgeons', 'Smart Watch Dealers', 'Drug De Addiction Centres'
                    ],
                },
                {
                    id: 4,
                    name: "we are working in cities",
                    route: "/place/",
                    sublinks: [
                        'Delhi', 'Mumbai', 'Bangalore', 'Hyderabad', 'Chennai', 'Pune', 'Ahmedabad', 'Kolkata', 'Jaipur',
                        'Chandigarh', 'Coimbatore', 'Lucknow', 'Surat', 'Indore', 'Patna', 'Nagpur', 'Ernakulam', 'Bhopal',
                        'Vadodara', 'Ludhiana', 'Kanpur', 'Nashik', 'Varanasi', 'Visakhapatnam', 'Rajkot', 'Raipur-Chhattisgarh',
                        'Vijayawada', 'Madurai', 'Ranchi', 'Goa', 'Thiruvananthapuram', 'Bhubaneshwar', 'Allahabad',
                        'Aurangabad-Maharashtra', 'Dehradun', 'Mysore', 'Trichy', 'Guwahati', 'Agra', 'Kozhikode', 'Jodhpur',
                        'Thrissur', 'Kolhapur', 'Salem', 'Meerut', 'Mangalore', 'Gorakhpur', 'Jabalpur', 'Jalandhar', 'Gwalior'
                    ]
                }
            ]
        }
    }
}
</script>
<style lang="">

</style>